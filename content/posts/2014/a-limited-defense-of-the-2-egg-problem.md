+++
date = "2014-11-25T22:07:59-08:00"
draft = true
tags = ["interviews", "math"]
title = "A limited defense of the 2 egg problem"

+++
There’s a lot of backlash against using problems to asses cleverness in interviews. So much so that it looks like the site that reminded me to write this article changed [their example](https://www.interviewcake.com/free-weekly-coding-interview-problem-newsletter) question away from the derided “2 egg problem”. 

> I believe it is the prime example of everything that is wrong with engineering interview culture. Not sure if that makes it ideal material for a site like this or pointless trivia. — Top comment in a Hacker News [thread](https://news.ycombinator.com/item?id=8565495)

Before I was the charming well-rounded jock that I am today\[citation needed\], I was essentially a mathlete, so questions like this give me the same warm fuzzy feelings as reading Dr Seuss books might give to a liberal arts major. But I’ve also done hundreds of interviews there’s one more thing that I’ve found:

How you solve an arbitrary stupid problem is a valuable thing to find out.

If you asked me this question, here’s the genre of answer that you’d get:

First call out your assumptions

* That each floor is equally likely to be the fatal floor. This is a biggie: common sense dictates that the [LD50](http://en.wikipedia.org/wiki/Median_lethal_dose)of a dropped egg is less than a meter, so the naive approach will work best (the egg will break on floor 1 or possibly 2, and we can all go home).
* You aren’t looking for a mathematical proof that my solution is optimal — this would be a huge undertaking, I can definitely give you some possible bounds on the optimal solution, and we might get lucky but it’s not a 60 minute problem. So we’re looking for the best solution I can find. This is valuable because it means we’re (correctly) focused on how I approach the problem)
* The metric we’re optimizing is expected number of floor drops: so time spent climbing down to collect unbroken eggs doesn’t matter and buying 2-dozen eggs to speed things up is out of scope. Also we aren’t looking to minimize the worst case (even though that’s often similar to minimizing the average case).

I’m also looking to tease out any extra information, [Google’s version](http://classic-puzzles.blogspot.com/2006/12/google-interview-puzzle-2-egg-problem.html) is very careful to call out all the details that you need, but interviewers are human.

It’s also worth noting that I’ve already made a mistake, the solution space to this problem (all possible egg dropping algorithms) [seems to be small enough](http://www.geeksforgeeks.org/dynamic-programming-set-11-egg-dropping-puzzle/) that we can try them all — Maybe I don’t belong at Google :)

Go looking for interesting angles

* If we had only one egg, we’d need to use the naive approach (dropping from floor 1, 2, 3 and so on). And at some point we’re going to be down to one egg, so we’re looking to use the first egg to minimize the number of floors we have to use the naive approach on.
* 100 is a square number, and we have 2 eggs. 100 is not a power of 2 (I don’t know if this is useful yet)

Prove that you can totally handle this  
So now let’s show off our basic math skills and mention that the naive approach will take 50 drops on average — it’s also O(n) and wastes an egg which are the two cardinal sins of search algorithms.

Ordinarily I’d go to a binary search next, but that feels too easy and I’m worried that half the time we’re going to break on floor 50 and that’s a lot of naive searching already. Also the two outcomes aren’t exactly similar (a broken egg means we lose resources). I wouldn’t mention it but I also don’t want to have to keep figure out how to round 100/2n.

Since 100 is square, I wonder if that’s relevant, so I’d look at moving up 10 floors each time with the first egg.

Ballparking this process, for floor XY, it’s going to be roughly X+Y+1 drops to determine that it’s the fatal floor, except floors X0 Where it will be X+9…

At this point, I’m going to cut off my hypothetical interview, since the cardinal rule in an interview question is to know what you’re looking to measure — and I can’t guarantee that I am looking to get the same things out of this question as the people who ask it.

My goal here isn’t to wow you with my arithmetical prowess. However, given that it’s hard in interviewing to find new but sufficiently uncorrelated things to ask a person, this genre of question can show a lot about your problem solving approach, even if you aren’t disrupting the SaaS egg-dropping space (YC15).

Not convinced? You can still [interview at PagerDuty](http://www.pagerduty.com/jobs), we don’t use this question.