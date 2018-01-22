---
layout: post
title: "Webscraping with Haskell"
author: "Chris"

---

# Haskell web scrapping

Webscraping with Haskell is surprisingly easy using [selenium](https://hackage.haskell.org/package/webdriver). I have been using Haskell to scrape homework assigments from my school's web assigment center. You will need to install the [webdriver](https://hackage.haskell.org/package/webdriver) package from [cabal](https://www.haskell.org/cabal/). The haskell webdriver package requires  [chromedriver](https://sites.google.com/a/chromium.org/chromedriver/)   to be in the [$PATH](https://askubuntu.com/questions/322772/how-do-i-add-an-executable-to-my-search-path) as well as having a running [selenium stand alone server](http://docs.seleniumhq.org/download/). Here's how to open a web page.
```haskell
    import Test.WebDriver
    import Test.WebDriver.Commands
    main = runSession ( useBrowser chrome defaultConfig) $ openPage "www.google.com"
```

To login you can use [waitUntil](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands-Wait.html) and [sendKeys](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html).
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

The ById [selector](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands.html#t:Selector) tells selenium to find an element by it's id. The [waitUntil](https://hackage.haskell.org/package/webdriver-0.8.5/docs/Test-WebDriver-Commands-Wait.html) is necessary because sometimes it takes longer for a web page to load. The [=<<](https://haskell-lang.org/tutorial/operators) pipes an element into a command. It could be rewritten as.
```haskell
    import Test.WebDriver
    import Test.WebDriver.Commands
    import Test.WebDriver.Commands.Wait
    main = do
    	 usernameLogin <- (waitUntil 20 $ findElem (ById "Username")
    	 sendKeys "creuter" usernameLogin
    	 passwordTextBox <- (waitUntil 20 $ findElem (ById "Password"))
    	 sendKeys "myPassword" passwordTextBox
    	 clickButton <- (waitUntil 20 $ findElem (ById "loginBtn"))
    	 click clickButton
    	 liftIO $ threadDelay 8000000
```

Once you've logged and the right cookies are set. You can navigate to another page.
```haskell    
    openPage "https://latinschool.myschoolapp.com/app/student#studentmyday/assignment-center"
    liftIO $ threadDelay 8000000
```

I then scraped the homework through  the findElems function which returns all the elements matching a given selector.
```haskell
    assigmentTable <- waitUntil 20 $ findElems (ById "assignment-center-assignment-items")  -- locate assigment table
    cells <- findElemsFrom (assigmentTable !! 0) (ByXPath "tr")  -- find all table data rows
    mocells <- mapM (\x -> findElemsFrom x (ByXPath "td")) cells -- locate all data columns withing rows
    mapM (\row -> mapM (getText) row) mocells -- returns text of homework table
```
The final Product. 

<script src="https://asciinema.org/a/6vkZdPqqrpJxooWZgiXhraPqq.js" id="asciicast-6vkZdPqqrpJxooWZgiXhraPqq" async></script>

The completed [source code](https://github.com/Chrisr850/scraping).