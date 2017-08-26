---
layout: post
title: "A (debatably) Brief Introduction to Python"
author: "Vedant Pathak"
---

CHAPTER 0: THE PYTHON FILE

Let’s start this introduction to python in the most generic way possible, shall we?
Using what you’ve learned from the command line, navigate to your development
folder (if you don’t have one, make one) and create a python file. Name it whatever
you want, but remember that **all python files end with the extension “.py”**, so your
filename should look something like [`<filename>.py`](https://stackoverflow.com/questions/8822335/what-do-the-python-file-extensions-pyc-pyd-pyo-stand-for). Open it up with whatever text
editor you like (I use sublime text), but keep your command line window open. Great.
Now, you have a blank python file.
The best part of all python files is that (at least in python 3), there is no need to create a
main function (more on functions later). Whatever code you write in the python file,
regardless of where it is located, will be run by the compiler. Of course, bespoke
functions will not be run unless called in the file. Speaking of which, let’s call python’s
built-in [`print()`](https://docs.python.org/2/tutorial/inputoutput.html) function on line 1 of our blank python file. It should look a little
```python
something like this:
print("Hello, World")
```


As is the case with all functions, the [`print()`](https://docs.python.org/2/tutorial/inputoutput.html) function processes whatever is inside the
parentheses. More on [`print():`](https://docs.python.org/2/tutorial/inputoutput.html) this function will pretty much output whatever is passed
through the parentheses, which makes it very useful for debugging.b
Now that we’ve got something in our python file, let’s do something with it! Go back to
your command line window and type in [`python <filename>.py`](http://pythoncentral.io/execute-python-script-file-shell/), of course replacing
[`<filename>`](https://stackoverflow.com/questions/8822335/what-do-the-python-file-extensions-pyc-pyd-pyo-stand-for) with whatever you named your file. The output should be identical to this:
```
Vedant's-Macbook-Pro Dant$ python intro.py
Hello, World
Vedant's-Macbook-Pro Dant$
```

If all goes to plan, congratulations! You have successfully created the aptly-named
“hello world” file, as made famous by Brian Kernighan and Dennis Ritchie – the creators
of C. Otherwise, please see me.
There is more that can be done while running python files, however! You can include
command line arguments, which is basically a series of words that follow [`python <filename>.py`](http://pythoncentral.io/execute-python-script-file-shell/). The cool thing about command line arguments is that you can do
things with them! We’re not far enough in this introduction to be able to do things with
them, however we can simply print them for now. There are many ways to handle
arguments, such as importing [`click`](http://click.pocoo.org/5/) or [`argparse`](https://docs.python.org/2/howto/argparse.html) ; however, for now, we’ll stick to [`sys`](https://docs.python.org/2/library/sys.html)for now. Hold on. Pause. What do I mean by importing? Let me explain. Certain
benevolent python developers have packaged a ton of pre-made code for us to use
into libraries. We can gain access to all of that code by simply adding [`import`](https://docs.python.org/3/reference/import.html)
AcmeMissiles at the beginning of our python programs. If we were to use any of the
library’s functions after importing it, we would acess that function/variable like so:
`AcmeMissiles.ShootMissiles(reallyBigOnes=True)`, or `AcmeMissiles.PointyMissiles`. For
reference, `reallyBigOnes = True` is known as an argument. In the case of [`sys`](https://docs.python.org/2/library/sys.html), in order to access all of the arguments typed in
while running the program, we would use  [`sys.argv`](https://docs.python.org/2/library/sys.html) to access the [`sys`](https://docs.python.org/2/library/sys.html) [`argv`](https://docs.python.org/2/library/sys.html) variable. If you complete assignment
0, you will realize that the arguments are organized in an odd manner. Let me explain.
What you see is a list: a python data structure that stores multiple instances of a certain
data type. I’ll discuss lists in greater detail in chapter 3. Until then, stay patient.
Also notice that the first element of sys.argv is the filename. Interesting, right? Not
really. Just keep that in mind going forward.