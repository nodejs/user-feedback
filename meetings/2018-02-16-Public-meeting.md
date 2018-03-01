# 2018-02-16 Public User Feedback Meeting - Node.js Benchmarking

## Links

* **Recording**: https://www.youtube.com/watch?v=BTiBmW83FMY 
* **GitHub Issue:** https://github.com/nodejs/user-feedback/issues/27
* **Previous Minutes:** https://docs.google.com/document/d/13kjBLpK3huHgCebxROpBNuUQLNyyOafaI5lOKi129Co/edit

## Present

- Dan Shaw (@dshaw - User Feedback lead, CommComm member)
- Mihai Ene-Pietrosanu (@mihaiep- User Feedback member)
- Tierney Cyren (@bnb - CommComm Co-Chair)
- Michael Dawson (@mhdawson - CommComm member, TSC Chair)
– Tracy Hinds (@hackygolucky – CommComm member, Leadership Subcommittee Chair)

* End users
  - Joel Chen (@jchip WalmartLabs)
  - Bradley Farias (@bmeck GoDaddy)
  - Aaron Bartell (Krengel Tech) 
  - Matvienko Nikolay (Grid Dynamics)
  - Tierney Cyren (NodeSource)
## Agenda

* Extracted from neuf-agenda labelled issues and pull requests from the user-feedback repo prior to the meeting.
* Introduction to the Benchmarking Working Group (WG) with @mhdawson
* Presentation of the Benchmarking Survey Results
* Detailed feedback from select attending representatives
* Open feedback forum
* Invited
    User Feedback team members
    * Dan Shaw (@dshaw - User Feedback, CommComm observer)
    * Mike Hostetler (@mikehostetler)
    * Mihai Ene-Pietrosanu (@mihaiep, User Feedback)
    * William Kapke (@williamkapke - CommComm, Individual Member Director)
    * Michael Dawson (@mhdawson - User Feedback, CommComm, TSC Chair)
    * Tierney Cyren (@bnb - User Feedback, CommComm Co-Chair)
    * Tracy Hinds (@hackygolucky - CommComm)
    * Greg Wallace (@gtewallace - Node.js Foundation)
    
    End User Representatives
    * Bradley Farias (@bmeck - GoDaddy)
    * Mohammad Khan
    * Tierney Cyren (Node Source)
    * Amanda Blackburn (Profound Logic)
    * Mittra, Partha (whisolutions)
    * Heckmann, Aaron (Paypal)
    * Aaron Bartell (Krengel Tech) 
    * Matvienko Nikolay (Grid Dynamics)
    * Jeremy Meyer (Jack Henry)
    * Bradley Meck (GoDaddy)

**TOPIC**
*  **Thanks** to our guests Bradley, Joel, Aaron, Nikolay, Tierney and thanks all for participation 
in first Public User Feedback-Node.js Benchmarking.
* Intro 
* **Michael Dawson: Introduction to the Benchmarking WG.**
   * What the Benchmarking Group is?  
   * Repo here: https://github.com/nodejs/benchmarking
    The focus: we want to track and evangelize performance gains
    between releases and avoid performance regressions. 
    Make sure Node is running efficiently.
1.  Define Use cases: https://github.com/nodejs/benchmarking/blob/master/docs/use_cases.md
 
If you have an use case that doesn’t fit into one of these here is important for you to let us know, 
so we can factor in additional use cases into the work we do here.
 
2. Key runtime attributes
https://github.com/nodejs/benchmarking/blob/master/docs/runtime_attributes.md
 
3. Case coverage (coverage of use cases and key attributes)-to track performance
https://github.com/nodejs/benchmarking/blob/master/docs/case_coverage.md.
The benchmarks running every night https://benchmarking.nodejs.org/. 
We have a dedicated number of machines running (donated by Intel and IBM); hardware machines vs virtual machines.
We will have a session at Community day @Index 2018, Feb 20/ free registration for that.
 
* **Dan Shaw: Benchmarking survey details**
  * Next meeting, we will have a debrief for survey, improvements, upgrades.
  * **Survey Q#2:** What version of Node.js do you currently use for production?
  
	    * Answered 294:
	      * 9.x Current 25%
    	  * 8.x LTS 74%
	      * 6.x LTS 38%
	      * 4.x LTS 12%
          * Pre 4.x 2%
      
* Bradley&Joel: we have 2 months lag time on LTS
* Joel: Start testing on applications internally after is promoted to LTS.
         We have half, half 6 and 8 versions.
* Bradley: Start testing before LTS
* Tierney: In your production environment how do you handle upgrades,
           security updates, patches?
* Joel: we are going with the entire update pull request,
           QA sign off and then deploy
* Bradley: pretty much the same
* Aaron: got recently 8.x, most of the platforms 6.x
* Nikolay: we have 8 version in production; using TurboFan Ignition boosted our performance
* Tierney: Is anyone actually using yarn either for dev or production?
* Joel: Has some issues that our build generally doesn’t work well. 
  In my testing with our real-word applications from 6 version to 8 version, 
  we saw a 60% improvement in performance
* **Survey Q#4:** What is your primary use case for Node?
  * 	**Answered 294:**
   	    * back-end API services 43%
      	* service oriented 3%
      	* microservice-based 19%
      	* generating serving dynamic 8%
      	* SPA applications 9%
      	* Agents and Data Collectors 2%
      	* Web Developer Tooling 9%
      	* Small scripts 1%
 * Joel:  we would like to see more on this case: 
 how to use Node direct connect to back -end databases,
 because now our apps when they need to connect DB they go through service that’s reading Java.  
 * Bradley: we don’t auto scale our build services, 
 we have service-oriented architecture with immutable builds
 
* **Survey Q#6:** Do you have infrastructure in place for tracking performance on your applications?
      	Answered 288: Yes 38%, Work in progress 30%, No 32%
* Joel: we have a logging to Splunk for general application: 
less about performance but more about the application health and monitoring 
usage on our website. APM infrastructure based on Kafka.
* Bradley: APMs running; need to be turned off in some cases 
in production due to leaking memory, essentially while they try to track events.
Reccomendation: include node report in all green applications 
(get some reports started last month).
* Nikolay: Splunk for logging, using New Relic as monitoring systems and to be ready for Black Fridays.
Monitoring systems are big impact on performance
 
**Survey Q#9:** What type of optimization passes do you run on your JavaScript you deploy it to Node.Js?
 	Answered 211: Minification 68%, Bundling 60%, Obfuscation 20%, Other 22%
  	
**Survey Q#16:** Do you have use cases where you cannot use Node.js because it is single threaded?
 	Answered 282: Yes 22%, No 78%
* Nikolay: anything that need to use cpu that’s a bottleneck
* Joel: a single threat definitely is something that we’re constantly trying to have to work around it, because we do e-commerce and the server can general do one to two requests per second    
 
## Questions, remarks:
* Michael: we can help with scripts for IBM I platforms/ running on same benchmark.
* Tierney: Should we provide a way to go in benchmark for like user land?
* Michael: Is something that users can contribute to cover up of our Matrix,
or something differently we can run and evaluate?  
* Joel: Happy to look in service-oriented architecture, 
most of our applications, majority work they do is making its service
cost to the back-end microservices.

Useful link: https://github.com/v8/web-tooling-benchmark
 
* Joel: We have a lot of trouble in terms of performance, 
stylus compounding, internally we use SAAS try our CSS and then 
we have the compiled massive piles and some of the deeply nested trees,
they take huge amount of time (nested structure).
* Michael: Comments that you might like SAAS compiler in the web tool?
* Bradley: There is one comment Go Daddy has had about this web tooling 
benchmark if you go and look how it runs all these benchmarks are requiring
that whatever they run be synchronous so that’s the reason webpack is not here,
so we’ve got our own stuff going separate of this. We have some build farms we run web pack.
* Bradley: another big part has been memory uses, when we have everything cached
at every node of our service-oriented architecture.    
* Michael: Sounds like 2 areas: maybe you’ll be able to contribute additional
benchmark we might want to be running for the web tooling side, 
then also if you have some specific things around memory in terms of measuring
it might be a good addition use case.
* Dan: when we talk about caching what are the bounds that you would look for there?
* Bradley: We have multi-tiered caches, so garbage collection 
can become a problem once we get into several gigabytes in size
for our caches some of them are running at 8 gigs for their cache size.
* Dan: It is a great way to begin exploring benchmarking usage. 
* Michael: If you have benchmarks and you want to pursue the discussion
with the Benchmarking WG you can may open an issue in the Benchmarking WG 
  
**Closing Thoughts**
* Dan: for questions or others Index 2018 is an opportunity to talk direct to people.
https://developer.ibm.com/indexconf/?cm_mmc=dw-_-social1711-_-redirect-_-indexconf
* Tierney: something we could improve on for the future correlating with 
size of company because a smaller company isn’t going to have more 
than a hundred applications in production.
* Dan: flag the discussion around diagnostic that touched pooling;
if pooling and pooling mechanism that are pain point computationally intensive.  
* Tierney: Monitoring systems are big impact on performance+security. 
* Michael: start a thread, because some users have concrete use cases, 
follow-up and get actually documented.
 
## Upcoming Meetings 2018-03-02
* The next meeting is scheduled for Friday, 2018-03-02 at 17:00 UTC / noon ET / 11am CT / 9am PT.
* https://github.com/nodejs/user-feedback/issues/32
* **Node.js Foundation Calendar**: https://nodejs.org/calendar
 - Click `+GoogleCalendar` at the bottom right to add to your own calendar.

