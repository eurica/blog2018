+++
date = "2014-09-16T22:16:38-08:00"
draft = true
tags = []
title = "Reporting time spent on PagerDuty incidents with notes (code sample)"

+++

I was talking with a [PagerDuty](http://www.pagerduty.com/) customer, and they track how much time they spend responding to an incident with a simple string like “30m” or “2h” in a note on the incident.

That makes it fairly easy with our API (and [PDJS](https://github.com/eurica/pdjs)) to pull and sum all the time spent on incidents. Here’s a script that pulls out all the notes mentioning times from incidents on my “webdemo” account for September 15th, 2014. (All the data is fake, of course).

[http://jsfiddle.net/eurica/oj4c7p2z/8/](http://jsfiddle.net/eurica/oj4c7p2z/8/ "http://jsfiddle.net/eurica/oj4c7p2z/8/")