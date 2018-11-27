+++
date = "2018-11-26T22:26:52-08:00"
draft = true
tags = []
title = "XKCD is the new Donald Duck"

+++
July 17, 2013 by dave

As a child, it bothered me the way that the Star Trek world interacted with technology; the idea that a human being would need to say “evasive maneuvers” made for an awful UI and a wild misunderstanding of how fast computers can shoot lasers at each other. Hidden from my bulky cathode ray emitting box, the real future was being [predicted by Donald Duck](http://www.cracked.com/article_19021_5-amazing-things-invented-by-donald-duck-seriously.html), and Randall Munroe is the Donald Duck of programmers.

Let’s start with what doesn’t count

* [Geohashing](http://xkcd.com/426/) uses a number that will only be available in the future (e.g. the closing price of a stock in a month) to generate a hash that maps to a place that won’t be known until the future. If he had left it as a comic, someone would’ve built it, but alas, Randall made a [reference implementation](http://carabiner.peeron.com/xkcd/map/map.html)
* If you changed your password because he [ran some numbers](http://xkcd.com/936/) for you, I’m not counting it either.

Even without those, here’s a list of things that a colour-less webcomic has sarcasmed into existence:

* [M-x butterfly](http://xkcd.com/378/), based loosely on a 1988 play by David Henry Hwang, made its way into emacs — it’s even animated!
* [import antigravity](http://xkcd.com/353/) seems to just [open up itself](http://svn.python.org/view/python/trunk/Lib/antigravity.py?view=markup&pathrev=66902) — unless you count [a geohashing algorithm](http://svn.python.org/projects/python/branches/pep-0384/Lib/antigravity.py)
* [Stacksort](http://xkcd.com/1185/) is nature’s perfect sorting algorithm: it connects to StackOverflow, searches for ‘sort a list’, and downloads and runs code snippets until the list is sorted. Best of all, [it actually works](http://gkoberger.github.io/stacksort/)
* There’s at least one [random shopping bot](http://randomshopper.tumblr.com/post/35454415921/randomized-consumerism) live in the world, spending its $50/month budget. Co-incidence? [I think not](http://xkcd.com/576/)
* [Up Goer Five](http://xkcd.com/1133/) (The only flying space car that’s taken anyone to another world) was the thing that made a guy make [this thing here](http://splasho.com/upgoer5/) ([Hamlet!](http://splasho.com/upgoer5/index.php?i=IT8tLzHto3Vtoz90VUEiVTWyYPO0nTS0VTymVUEbMFOkqJImqTyiowbtVNcKnTI0nTIlVTy0VTymVTWyqUEypvOcovO0nTHtoJyhMPO0olOvMFObqKW0VNcPrFO0nTHtpTScovO0nTS0VTkcMzHtqTulo3qmVTS0VUyiqFjtPx9lVUEiVUEun2HtLKWgplOuM2ScoaA0VTkcMzHaplO0pz91LzkypjcOozDtMJ5xVUEbMJ0tLaxtMz9lL2H/VPOHolOxnJHfVUEiVUAfMJIjBlNXGz8toJ9lMGftLJ5xVTW5VTRtp2kyMKNtqT8tp2S5VUqyVTIhMNcHnTHtnTIupaDaplOjLJyhVTShMPOuoTjtqTuyVT1uoaxtp2uiL2gmPyEbLKDtL29gMFO0olOfnKMcozptnUIgLJ5mYvNtFKDtnKZtLJ4tMJ5xnJ5aPzI2MKW5o25yVUAbo3IfMPO3LJ50YvNtIT8tMTyyYPO0olOmoTIypQfXIT8tp2kyMKN6VUOypzuupUZtqT8tMUWyLJ06VUyypljtqTuypzHaplO0nTHtpaIvBjcTo3VtnJ4tqTuuqPOmoTIypPOiMvOxMJS0nPO3nTS0VTElMJSgplOgLKxtL29gMDcKnTIhVUqyVTuuqzHtp2kcpUOyMPOiqKDto2Lto3IlVTWiMTyypljXGKImqPOgLJgyVUImVUA0o3NtLJ5xVUEbnJ5eYvNtITuuqPqmVUEbMFOlMJSmo24XITuuqPO3MFOeMJIjVTqinJ5aVUEbpz91M2ttoTyzMFqmVUOlo2WfMJ1mYtcTo3Vtq2uiVUqiqJkxVUEun2HtqTygMFqmVTu1paEcozptLJqunJ4tLJ5xVTSaLJyhYNcHnTHtoJIuovOgLJ4aplOvLJDtLJA0YPO0nTHtnTyanPOgLJ4aplOvLJDtq29lMUZfPyEbMFOjLJyhVT9zVT9hMF1mnJEyMPOfo3MyYPO0nTHtq2ScqPOzo3VtqUW1qTtfPyEbMFO3pz9hM3Zto2LtqTuip2HtnJ4tpT93MKVtLJ5xVUEbMFOvLJDtqTucozqmPyEbLKDtM29iMPOjMJ9joTHtp2uiqJkxVT5iqPObLKMyVUEiVUEun2HfPyqbMJ4tnTHtnTygp2IfMvOgnJqbqPOyozDtnKDtq2y0nPOuVTA1qQ8XI2uiVUqiqJkxVTAupaW5VUAioJI0nTyhMlObMJS2rFjXI291oTDtqTylMJDtLJ5xVTuiqPOjqJkfVTy0VUEbpz91M2ttoTyzMFjXDaI0VUEbLKDtqTuyVTMyLKVto2Ltp29gMKEbnJ5aVTSzqTIlVTEyLKEbYNcHnTHtp3ElLJ5aMFOjoTSwMFOzpz9gVUqbnJAbPx5iVT9hMFOlMKE1pz5mYPObo2kxplO0nTHtq2yfoPOcovOwnTIwnjcOozDtoJSeMKZtqKZtp3EurFO3nKEbVUEbMFOjpz9voTIgplO3MFObLKMyPyEbLJ4tMzk5VUEiVT90nTIlplO0nTS0VUqyVTgho3ptoz90VT9zCjcWovO0nTymVUqurFOiqKVtoJyhMUZtn2IypPO1plOcovOzMJSlBjcOozDtnJ4tqTucplO3LKxto3IlVT93ovO0paIyVUOiq2IlPxymVT1uMTHtp29zqPOuozDtp2ywnlOvrFO0nTyhn2yhMl4XDJ5xVTqlMJS0VTygpT9lqTShqPOjoTShpjcPrFOmqJAbVUEbo3IanUEmVTSlMFO0qKWhMJDtLJ5xVTkip3DtPxShMPOupzHtoz90VTSwqTIxVT9hYtcCnPRtVRuypzHtnKZtqTuyVTWyLKI0nJM1oPOanKWfVDcWovO5o3IlVUAiozqmVTWyVTSfoPOgrFOzLKIfqUZtpzIgMJ1vMKWyMP4=)).
* Code to [play meta-regex golf](http://nbviewer.ipython.org/url/norvig.com/ipython/xkcd1313.ipynb) by [Peter Norvig](http://en.wikipedia.org/wiki/Peter_Norvig)
* [XKCD 806](http://xkcd.com/806/) proposes a system where saying “shibboleet” on a tech support call indicates that the caller is tech-savvy and they are transferred out of the standard script to a person who knows a minimum of 2 programming languages. An [ISP](http://revk.www.me.uk/2010/10/xkcd806-compliance.html) in the UK is proudly XKCD/806 compliant.
* Munroe keeps a page of [people recreating](http://xkcd.com/chesscoaster/) [XKCD 249](http://xkcd.com/249/)

I was sadly unable to secure funding for cat-proximity testing.

[![cat_proximity](http://euri.ca/wp-content/uploads/2013/07/cat_proximity.png =450x439)](http://xkcd.com/231/)