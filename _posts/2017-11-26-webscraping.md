---
layout: post
title: "Webscraping with Haskell"
author: "Chris Reuter"
---

# Haskell web scrapping

I webscraping with Haskell is surprisingly easy using the [selenium webdriver](https://hackage.haskell.org/package/webdriver). I used it to scrape home work from my school site. To launch a browser session use

    run Session defaultConfig :: WD a -> IO a

To run these you will need to install [chromedriver](https://sites.google.com/a/chromium.org/chromedriver/) as well as having a running [selenium stand alone server](http://docs.seleniumhq.org/download/). Here's how to open a web page.

    runSession ( useBrowser chrome defaultConfig) $ openPage "www.google.com"


To login you can use waitUntil and sendKeys.

    openPage "https://latinschool.myschoolapp.com/app#login"
    sendKeys "creuter"  =<< (waitUntil 20 $ findElem (ById "Username"))
    sendKeys "myPassword"  =<<(waitUntil 20 $ findElem (ById "Password"))
    (waitUntil 20 $ findElem (ById "loginBtn")) >>= click

The ById command tells selenium to find an element by it's id. The waitUntil is necessary because sometimes it takes longer for a web page to load. The =<< pipes an element into sendkeys. It could be rewritten as.

    usernameLogin <- (waitUntil 20 $ findElem (ById "Username")
    sendKeys "creuter" usernameLogin
    passwordTextBox <- (waitUntil 20 $ findElem (ById "Password"))
    sendKeys "myPassword" passwordTextBox
    clickButton <- (waitUntil 20 $ findElem (ById "loginBtn"))
    click clickButton
    liftIO $ threadDelay 8000000


Once you've logged and a session is set. You can log in somewhere else.
    
    openPage "https://latinschool.myschoolapp.com/app/student#studentmyday/assignment-center"
    liftIO $ threadDelay 8000000

You can then scrape homework through findElems.

    assigmentTable <- waitUntil 20 $ findElems (ById "assignment-center-assignment-items")  -- locate assigment table
    cells <- findElemsFrom (assigmentTable !! 0) (ByXPath "tr") 
    mocells <- mapM (\x -> findElemsFrom x (ByXPath "td")) cells
    mapM (\row -> mapM (getText) row) mocells -- returns text of homework table

Example usage.

[![asciicast](https://asciinema.org/a/gXSECM7LwipXgA7hgEx1WB11m.png)](https://asciinema.org/a/gXSECM7LwipXgA7hgEx1WB11m)