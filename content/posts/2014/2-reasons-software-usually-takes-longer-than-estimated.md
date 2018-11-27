+++
date = "2018-11-26T22:18:17-08:00"
draft = true
tags = []
title = "2 reasons software usually takes longer than estimated"

+++
September 15, 2014 by dave

Like many people whose jobs involve getting software out the door, I think a lot about why we usually ship late (and never early). Unfortunately my theory is pretty mundane — the less accurate the estimate, the more likely it is to be late rather than early.

1\. Errors don’t cancel out. A simple example: If a half of the tasks in a project take twice as long as you expect, and the other half take half as long — rather than being on time, your project took 25% longer than scheduled[1](http://euri.ca/2014/why-software-usually-takes-longer-than-estimated/index.html#fn-1336-1). Unfortunately, to compensate for 1 task taking twice as long as you thought, you need to come in 50% under for 2 other similar sized tasks. The numbers are correspondingly worse if you’re off by a larger multiple.

2\. The [winners curse](http://en.wikipedia.org/wiki/Winner's_curse) is very hard to avoid. Generally the same team working with the same tools in the same problem space is going to have very similar cost benefit ratios for the top items on their backlog. The top projects on your backlog have costs of X1…XN and values of Y1…YN. Assuming that you’ve done your homework, you’ve ordered them so that X1/Y1 > X2/Y2 > … > XN/YN — in reality it’s likely closer to the truth that X1/Y1 = X2/Y2 = … = XN/YN. In words: you’re most likely to do the projects, or parts of a project that you’re the most optimistic about — so half the time, you’re picking a project because you’re overly optimistic about how long it will take.

What can we do instead?

One of my favourite aspects of Agile is the frequent demos with a process for re-prioritizing tasks, but even on a waterfall project there’s a simple rule of thumb that I like:

By the halfway mark[2](http://euri.ca/2014/why-software-usually-takes-longer-than-estimated/index.html#fn-1336-2) on a schedule:

* Someone not working on the project/feature must’ve successfully used the feature
* You have a finite, prioritized and shrinking list of remaining features and bugs
* You have a line that separates blockers from non-blockers and most of your effort is going towards blockers

The goal is to control as much as you can — if you can’t predict when a project will be done, you can at least put yourself in a position to decide between launching on time or launching with all the bells and whistles (or somewhere in between).

Some better answers:

* [Why are software development estimates regularly off by a factor of 2-3 times?](http://www.michaelrwolfe.com/2013/10/19/50/)
* [Software estimation considered harmful?](http://gigamonkeys.wordpress.com/2007/04/26/estimation-considered-harmful/)
* [What We Do and Don’t Know about Software Development Effort Estimation](http://www.infoq.com/articles/software-development-effort-estimation)

1. 50% x 2 + 50% x 1/2 = 125% [↩](http://euri.ca/2014/why-software-usually-takes-longer-than-estimated/index.html#fnref-1336-1)
2. I remember once being asked to bid on a project that was “90% finished” and dutifully (and I strongly suspect, correctly) estimated that we’d have to basically start over and do 100% of the project. [↩](http://euri.ca/2014/why-software-usually-takes-longer-than-estimated/index.html#fnref-1336-2)

Categories: [product management](http://euri.ca/category/product-management/index.html) | Tags: [making software](http://euri.ca/tag/making-software/index.html), [ur doing it wrong](http://euri.ca/tag/ur-doing-it-wrong/index.html) | [Permalink](http://euri.ca/2014/why-software-usually-takes-longer-than-estimated/index.html)