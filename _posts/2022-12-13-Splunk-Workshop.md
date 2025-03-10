---
published: true
---
## Splunk For Rookies
I took part in a webinar hosted by Splunk which provided hands-on exercises in a Splunk instance unique to me.

The virtual workshop consisted of several tasks including; Investigating successful vs unsuccessful web server requests over time, Showing the most common custoemr operating systems, and showing website activity by geographic location


### Building An App

By building an App we are able to customize content and capabilities for a variety of technologies and use cases. In the virtual workshop we created a unique app that contained one main dashboard with four panels. After creating a new app we added pre-loaded data into the Splunk instance, and configured Splunk to monitior some sample web server logs; that were being generated on the same server that Splunk was running.


****This is where you can specify where you would like to pull data from****

![ConfigData.png]({{site.baseurl}}/images/ConfigData.png)


By choosing Monitor, we then configured the App to pull data from the webserver that was running in the Splunk instance. However we could also use a Splunk forwarder to injest data via Files, TCP/UDP, or scripts. Or we could simply upload log files directly from our local machine.

Splunk is different from other SIEM systems un that it allows for all types of data injest


### Creating A New Dashboard and Populating It With Searches

During the Virtual Workshop we ran several searches in order to create a dashboard which displayed relevant data for different departments within an organization. 

For the IT Operations team we created a graph with successful vs unsuccessful web server requests over a given period of time.

For the DevOps team we created an area chart with the most common customer operating systems as well as which web browsers are experiencing the most failures.

And for the Security teams we created a geographical map which showed website activity by location, as well as showing the lattitude/longitude coordinates.

****Here is what our dashboard looked like by the end of the workshop****

![Dashboard.png]({{site.baseurl}}/images/Dashboard.png)

### Additional Searches

While the data that is being injested by Splunk is limited in the virtual workshop, I wanted to add another stream of data that a security team could use. 

I decided on creating a graph that would report that would represent all POST requests from Linux Machines to the webserver as Linux distributions are commonly used among attackers and POST requests are susceptible to attacks such as HTTPS request smuggling. 

**To return events that satisfied both the POST and Linux conditions I used the following command.**

![command.png]({{site.baseurl}}/images/command.png)

To create visualization of this data I created a statistics that represented the top 5 different useragent of the events and saved it to the dashboard.

![POST requests from Linux.png]({{site.baseurl}}/images/POST requests from Linux.png)


### Takeaways

Overall the workshop was well structured and provided a macro-level overview of how Splunk can be used within an organization for valuable insights to different departments.

Having your own instance of Splunk allowed you to run any searches that you want and play around with creating apps without fear of breaking anything; but was limited with the kind of data that was injested.

I look forward to getting other logs injested into Splunk in order to create searches for other Indicators of Compromise.
