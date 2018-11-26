---
title: Don’t tell me you’re working on “Technical Debt”
date: 2018-09-18 07:00:00 +0000
categories: Development
tags: ["Rambling", "Code"]

---
That’s a category of work not a thing in and of itself.

Tell me what, why and why now:

* We’re upgrading our database library because we’re 2 versions behind and in 3 months it will no longer get security updates.
* We’re upgrading the data object model library at the same time since it’s 4 versions behind and we’re having trouble getting answers to our edge cases.
* We’re preemptively upgrading our serialization library because it’s trivial when we do the other work and saves us 10x the work next year.
* We’re redoing our web front end because if you don’t change you JavaScript framework every 2 years you can’t hire devs in San Francisco.
* We’re changing our rendering pipeline because I’m used to another one and weeks of work could save hours of reading the documentation.
* We’re doing a sprint of p2 and p3 bugs because we’re below our quality bar, they are drowning our real p1s and slowing dev. Now’s a good time because we’re blocked on the API team.
* We’re caching some data locally because we’ve found a dependency on a 3rd party API can cause us to hard 500. We didn’t expect this vendor to go down for more than a few minutes, but they had a 30 hour outage last month.
* We took some shortcuts to get customers using a feature, but we only tested it with up to 100 users, we’ll probably hit that point in a month so we need to scale before then.
* We’re doing some security hardening; after a team discussion we suspect we may be vulnerable to SQL injection attacks.
* We are changing our framework, because it’s fun and we sense weakness in the organization so if we get part of it into production while product & marketing are fighting then we’ll be stuck finishing it.

Some of these are obviously better than others.