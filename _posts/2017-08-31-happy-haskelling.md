---
layout: post
title: "Happy Haskelling"
author: "Chris Reuter"
---

# What's Haskell?

Haskell is a functional programming language that allows you to write really precise, simple and easy to understand code. Functional programming is a style of programming that combines functions together in order to tell the computer what to do. What's a function? Wikipedia tells that a function is a relation where ["each input is related to exactly one output"](https://en.wikipedia.org/wiki/Function_(mathematics)). The following are some examples.


| X | Y |
| --- | --- |
| 1 | 2 |
| 2 | 3 |
| 3 | 4 |
| 4 | 3 |
| 1 | 2 |

Each input maps to one output. Note having the same output from the different outputs is allowed.

| First Name | Last Name |
| --- | --- |
| Alonzo | Church |
| Haskell | Curry |
| Alan | Turing |
| Moses | Schönfinkel |
| J. Roger | Hindly |
| Robin | Milner |


Functions can apply to more than just numbers. They are just mappings between two groups with the special constraint of one member of one group can't map to two members of the second group.

| Dog pictures | Cuteness from 1-10 |
| --- | --- |
| ![dog](http://cdn3-www.dogtime.com/assets/uploads/gallery/goldador-dog-breed-pictures/puppy-1.jpg ) | 8 |
| ![dog](http://static.ddmcdn.com/en-us/apl/breedselector/images/breed-selector/dogs/breeds/bernese-mountain-dog_03_lg.jpg)| 9 |
| ![dog](http://cdn2-www.dogtime.com/assets/uploads/2011/01/file_23020_dachshund-dog-breed.jpg) | 8 |
| ![dog](https://vetstreet.brightspotcdn.com/dims4/default/79f1bd2/2147483647/crop/0x0%2B0%2B0/resize/645x380/quality/90/?url=https%3A%2F%2Fvetstreet-brightspot.s3.amazonaws.com%2F83%2F9e8de0a7f411e0a0d50050568d634f%2Ffile%2FPembroke-Welsh-Corgi-3-645mk62711.jpg) | 10 |

The trick of functional programming is that by using functions, in the strict math sense, understanding code is easier. Since it is all functions, you can be sure that every time you put the same thing into the function you'll get the same thing out. This is known as [referential transparency](https://wiki.haskell.org/Referential_transparency), and it makes understanding functional programs a breeze.

There is a stigma around FP [from now on functional programming will be known as fp, because I got tired of typing it out] that it is for ["pointy headed academics"](https://en.wikipedia.org/wiki/Simon_Peyton_Jones). Fp, however is easier to write and understand because of [referential transparency](https://wiki.haskell.org/Referential_transparency).

However FP has a significantly steeper learning curve than other languages like python.

![curve](http://i.imgur.com/TTBBeJs.jpg)

Haskell is one of the more [popular](https://insights.stackoverflow.com/survey/2017#technology) fp languages. It has been gaining traction in industry, most notably in [Facebook](https://code.facebook.com/posts/745068642270222/fighting-spam-with-haskell/). Haskell is kind like the [red pill](https://en.wikipedia.org/wiki/Red_pill_and_blue_pill) from the Matrix it changes your [perspective](https://stackoverflow.com/questions/775726/whats-the-fuss-about-haskell) on all other programming languages. Haskell also has strong ties to the mathematical domain of [category theory](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/). So you get to learn some new math terminology to impress and bemuse your math teachers! For instance [Zygohistomorphic prepromorphisms](https://wiki.haskell.org/Zygohistomorphic_prepromorphisms) sound pretty impressive, though they probably don't make you very fun at parties.

Haskell will make you a [better](https://www.reddit.com/r/haskell/comments/3absc6/how_did_haskell_make_you_a_better_programmer/) [programmer](http://dubhrosa.blogspot.co.uk/2012/12/lessons-learning-haskell.html?m=1). If you come from the imperative world, Haskell will feel weird and unintuitive at first. If you do a lot of math and have no experience with programming it will feel like an extension of math. Haskell is also blazingingly [fast](https://stackoverflow.com/questions/35027952/why-is-haskell-ghc-so-darn-fast).

If you want to take the proverbial red pill you should read my follow up blog posts.


