---
layout: post
title: "Webscraping with Haskell"
author: "Chris"

---

# Haskell web scrapping


Webscraping with Haskell is surprisingly easy using [selenium](https://hackage.haskell.org/package/webdriver). Using Haskell to scrape homework assignments has allowed me to circumvent my school's unwieldy assignment center. To do this you will need to: install the [webdriver](https://hackage.haskell.org/package/webdriver) package from [cabal](https://www.haskell.org/cabal/), install [chromedriver](https://sites.google.com/a/chromium.org/chromedriver/) and make sure it's in the [$PATH](https://askubuntu.com/questions/322772/how-do-i-add-an-executable-to-my-search-path) as well as having a running instance of [selenium stand alone server](http://docs.seleniumhq.org/download/). Once you're set up trying opening a web page with this Hello World code.

```haskell
    import Test.WebDriver
    import Test.WebDriver.Commands
    main = runSession ( useBrowser chrome defaultConfig) $ openPage "www.google.com"
```

The login page for my school's assignment page is a simple form. So we can use [sendKeys](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html) to fill out the appropriate text boxes.  Using the [ById](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html) allows us to select the appropriate text boxes by it's id. [waitUntil](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands-Wait.html) allows you to avoid errors, by waiting until the page is fully loaded before it tries to fill the text boxes.

```haskell
    import Test.WebDriver
    import Test.WebDriver.Commands
    import Test.WebDriver.Commands.Wait
    main = do
   	openPage "https://latinschool.myschoolapp.com/app#login"
       	sendKeys "creuter"  =<< (waitUntil 20 $ findElem (ById "Username"))
            sendKeys "myPassword"  =<<(waitUntil 20 $ findElem (ById "Password"))
            (waitUntil 20 $ findElem (ById "loginBtn")) >>= click
```

Once you've logged and the right cookies are set. You can navigate to another page, because the browser has already been authenticated. In this example I navigate to the url for the assigment center.

```haskell    
    openPage "https://latinschool.myschoolapp.com/app/student#studentmyday/assignment-center"
    liftIO $ threadDelay 8000000 
```

The [findElems](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html) returns the table element. An element is Selenium abstraction that represents different parts of the page. The [findElemsFrom](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html) function allows me to find all the data rows from the table. I then use the [findElemFrom](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html) again to get both columns from each row using the html td tag.

```haskell 
    assigmentTable <- waitUntil 20 $ findElems (ById "assignment-center-assignment-items")  -- locate assigment table
    cells <- findElemsFrom (assigmentTable !! 0) (ByXPath "tr")  -- find all table data rows
    mocells <- mapM (\x -> findElemsFrom x (ByXPath "td")) cells -- locate all data columns withing rows
    mapM (\row -> mapM (getText) row) mocells -- returns text of homework table
```
The final product in action, it takes a while but it gets there.

<script src="https://asciinema.org/a/6vkZdPqqrpJxooWZgiXhraPqq.js" id="asciicast-6vkZdPqqrpJxooWZgiXhraPqq" async></script>

The completed [source code](https://github.com/Chrisr850/scraping).
