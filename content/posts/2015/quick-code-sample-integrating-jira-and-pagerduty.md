+++
date = "2018-03-06T21:46:52-08:00"
draft = true
tags = ["heroku", "jira", "pagerduty", "code", "webhooks"]
title = "Quick code sample: Integrating JIRA and PagerDuty"

+++
Here is a program I threw together to create PagerDuty incidents that track urgent JIRA issue. The PD incidents are updated and closed automatically if the JIRA issue changes.

**Step 1, configure PagerDuty**
Create a generic API service in PagerDuty, and note the service key

**Step 2, Deploy to Heroku (optional)**  
You can test with my Heroku instance (jira2pd.herokuapp.com) or deploy it yourself by clicking here:  
[Deploy to Heroku](https://heroku.com/deploy?template=https://github.com/eurica/jira)

Configure your JIRA [webhooks](http://blogs.atlassian.com/2012/10/jira-5-2-remote-integration-webhooks/) with the URL: [https://jira2pd.herokuapp.com/jira/abc123](https://jira2pd.herokuapp.com/jira/abc123 "https://jira2pd.herokuapp.com/jira/abc123") where “abc123″ is the service key for your PagerDuty service

**Step 3, configure JIRA**

![](/uploads/WebHooks_-_JIRA1.png)

**Step 3b, Choose what issues trigger PD Incidents**  
JIRA can send webhooks on all incidents that match a piece of JQL, for instance

> project = HD AND priority in (“Needs Immediate Attention”, “P1 – Major / Must have”)

Will trigger on any ticket that gets created or moved to our HelpDesk team (HD) that has its priority set to urgent or P1.

**Step 3c, Configuration**

* Make sure that the webhook is configured to fire when an issue is “created, updated or deleted”
* Do not check “Request with empty body will be sent to the URL. Leave unchecked if you want to receive JSON.”
* You can test your JQL as a search to see what issues would have

**Postscript**  
Questions can be sent to [developers@pagerduty.com](mailto:developers@pagerduty.com), as always thanks go out to [Runscope](https://www.runscope.com/) for helping me debug my webhook traffic.