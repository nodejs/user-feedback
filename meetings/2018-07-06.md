# Node.js Foundation User Feedback Meeting 2018-07-06
## Links

* **Recording**: https://www.youtube.com/watch?v=ehTHsDTGbRM
* **GitHub Issue**: #76
* **Minutes Google Doc**: Doc
* **[Promises Github Issue](https://github.com/nodejs/user-feedback/issues/77)**

## Present
* Dan Shaw - @dshaw 
* Benjamin Gruenbaum - @benjamingr
* Ahmad Nassri - @AhmadNassri
* Mihai Ene-Pietrosanu - @mihaiep
* Michael Dawson - @mhdawson
* Tierney Cyren - @bnb
* Jordan Harband - @ljharb

* User Feedback Members: @nodejs/user-feedback

## Agenda

## Announcements

* Extracted from **user-feedback-meeting** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/user-feedback

* Public User Feedback request - European General User Feedback at WorkerConf [#56](https://github.com/nodejs/user-feedback/issues/56)

## Q&A, Other

## Notes
* **Many thanks to our guests today Benjamin, Ahmad and Jordan.**
* Intro by Dan Shaw
* Dan: Promises: at the Berlin summit, bunch of folks introduced to user feedback initiative and we invited to come and participate,
  one of the most active and organized groups it was the group that Benjamin had around Promises, we are trying to understand 
  where we are with Promises and what the desired outcome, Benjamin and some others would like to achieve and get feedback on.
* Benjamin: At the moment there are a bunch of usability issues and debugging experience isn’t exactly where we wanted to be;
  one of the things I have done before the meeting was to survey like some people try to get a better understanding of how
  the community has been using Promises and another thing that we have done is that we got a bunch of people together
  who have different viewpoints around what our APIs, and what we should do; one of the next steps we want to take is to try 
  and survey the community to understand like we have several technical options and we have discussed like the implications 
  of implementing them and I think at this stage you want some feedback from the community to better understand what users 
  are expecting in certain patterns like namely what should and rejections do and like what default behavior should be and 
  also like what sort of patterns people are using, what befalls they’re running into, because we have some interesting 
  conclusions from the research we’ve done so far and at this point we want to validate it against larger Node.js community.
* Dan: Jordan do you want to add anything in there? I almost immediately rates for: “yes we could standardized APIs 
  but are there any sort of Promises standardization workflows happening in standard space” maybe you could fill us in on that.
* Jordan: I don’t know any standards workflow currently being done that would impact the debug ability story around Promises.
  What I usually hear is, from folks in node core primarily and almost exclusively is that debugging Promises is terrible 
  and has always been, and that was a large part of the reason for the pushback against promise based things, but I don’t
  think anyone outside of core have really shared that opinion and I don’t think there is a huge debug ability problem with
  Promises this comes up a lot around unhandled rejections for example like desire to exit the process when there’s unhandled
  rejection things like that so I don’t think anyone would argue with “let’s make debugging anything better” and async code
  inherently is harder to debug than sync code; there’s always something that needs to be improved there and any work that
  we can do to improve it, should be considered. There’s a often a painted picture that things are on fire.
* Tierney: Having talked to my co-workers to go on site to large enterprises and deal with people using Promises,
  it’s not necessarily user code its third-party code and you don’t know when you’re pulling in a bunch of modules you can’t
  guarantee that they’re handling Promises appropriately so that makes a hard story.
* Jordan: Certainly if you’re pulling modules that are using code that are writing subpar code then your experience is going 
  to be impacted, but I feel there’s a pretty big leap from there to say that like as it relates to unhandled projection
  and exiting the process even though we’re not; I don’t think anyone’s proposing that happened immediately anymore, 
  but like there, I think there’s a big gap between other people’s code can misbehave and let’s violate what I argue is the
  intent of the spec so like kill the process immediately when there’s an unhandled rejection, and so I feel like I’ve in 
  general have been reacting what I see is that large gap between here’s a problem and then someone folks assume that this 
  is a solution, but the solution is burning more bridges than it’s saving.
* Dan: I seen that and adding to what Tierney said, it’s often the practitioners that are tasked to sort of get code on 
  messed up and Promises code tends to exacerbate that situation, the immovable point that I’ve seen around Promises have 
  come from teams that have gotten to a point of getting enough observe in their systems, through callback wrapping and 
  various other techniques.
* Benjamin: Another big part is that the V8 team has been very cooperative and pretty grating like taking feedback we give
  them seriously and improving things in the engine like async stack traces in production and then the ability to inspect
  the stock in production, I think a big improvement; now while things are getting better and there are already a lot better 
  than they were with callbacks at least for the big crowds. I still try to like monitor the Promises tagged in stack 
  overflow so there are things I still it are getting brought up a lot and we’re asking the V8 team for their time in implementing
  stuff and they started like implementing different warnings and like things occur often for us which is very of them 
  to dedicate that time, but I want to make sure that we’re not wasting time and things that like my intuition or like
  a not personal intuition which is why I think it’s really important that Jordan is here. 
  The next step is try to figure it out good questions to ask and we would love  your guidance; get the survey out so we can bring
  it up in the meetings we have with the V8 team.
* Dan: Ahmad is representing enterprise and has large deployment of node, is our guard Promises a problem, start with this
  kind of the broadest question.
* Ahmad: I don’t really hear too much complaints or see kind of situations where like our deployment or our application 
  development is affected by that, but I think it only becomes a problem in the context of inconsistencies and debugging
  as we said, it’s not great, but I would echo the point it’s not a burning problem; the nicest thing a developer has to do 
  in terms of debugging issues when they have to deal with code that’s mixed between Promises and non Promises especially 
  when it comes down to the native node APIs.
* Dan: Michael what the current approach TSC is having to dealing with them promised APIs?
* Michael: At this point its sort of experimental state where we’re at or different people are adding a couple, so far,
  it’s up to us and DNS it’s sort of experiment and get a feel for what works and what doesn’t as prelude to making more 
  organized effort to cover the broader surface area. My understanding of the discussion around the debug ability is that 
  the challenge is, you know, without before Promises if you had an unhandled exception it was easy to track that down because 
  you could set it up so you got an exception when that happens in the case of Promises because the way I handled rejections
  respect that’s much more difficult, so if people tasked with tracking down say intermittent or production problems we’re used
  to that tool which they had that was that they found effective, getting cored out and being able to look at the stock and 
  then going back the developers, not having that is a challenge for them. I also agree that breaking the spec it’s not 
  the obvious choice either, so it’s trying to figure it out what will let people debug and identify the location of those
  problems while maintaining how about we were needed.
* Benjamin: One of the things that I’ve been seeing it’s that very few people like when I asked the question which is easier
  for you to debug like Promises the same functions or like Promises without us think about a single weight or callbacks,
  like almost everyone in the crowd said I can pull the data but almost everyone in the crowd said that a sync functions
  are easier to debug than callbacks and then Promises were about as hard for the people that I question, this is like 
  another thing that we can ask, because very few people it’s very predominant in core but I don’t feel that this is the
  case for user base.
* Michael: It’s like kind of debugging, we need to make sure we have questions when we go out to capture who we’re talking to,
  because I’ve seen quite often the broader it is in a lot of cases it sounded like the broader or developers don’t have 
  to debug those issues you’re not the one pulled in to be both the issues and in production, so we may talk to a large
  portion of the users and it’s like well it’s no different because they’re not actually the ones enough to debug those
  kind of problems in production. It’s just a matter of understanding, it’s that it’s not an issue but I think we need
  to get the right people answering as opposed to but it or to be confident that we’re asking the right people before
  we decide it’s not.
* Dan: Benjamin what are the things that you know distract from a meaningful discussion around Promises?
* Benjamin: I think there’s a bunch of interesting discussion around Promises right now, Netflix are like have committed 
  to spend effort on getting like the postmodern debugging story better and having meetings on that and we like thing are moving
  not very quickly, but they’re moving, so that part is working well and then we want to get to a point where we are comfortable
  with the debugging experience people have now, that isn’t to say like debugging Promises is easy or hard but it’s what
  people are using like pharmacists are effect at this point and we need to improve; there was so much resistance over 
  so much time to Promises in core a part of that reflected them that we haven’t spent traditionally a lot of time as a 
  project discussing what the debugging experience should be; there have been certain individuals that have spent a lot 
  of time on that, but we haven’t done the discussion as a project so we’re starting to get some discussion going and just
  the fact that three people here have very different experiences that are all valid about how people are using/debug
  Promises is just a strong indication that the data would be very useful.
* Dan: I guess the thing that I’m probing for is establishing signal around Promises do we need to avoid or embrace async/await?
* Benjamin: I think we need to embrace async await, this is my opinion.
* Jordan: I think async/await is Promises but is not even all Promises it’s like async function is awesome because it’s a 
  static way to guarantee that a per function returns a promise and never throws but await I find to be actually terrible 
  in practice it’s only used easily, very tempting to accidently create a serialized second set of async actions when most
  of them could be parallelized in other words, the advice I give people is don’t ever change your Promises make each promise 
  be a separate variable and then when you are done you can combine chains if it makes sense everything that’s a chain you can 
  write in terms of a weight; in my experience if you followed that order where you don’t type a weight ever until the very last 
  step then you end up with maximally parallelizable or concurrent code and avoid accidently chaining things that don’t need to
  be changed; I don’t understand how you would be able to optimize async/await  both at the same time.
* Async/await is promises you await Promises like async reductions waiting for return promises and it’s like always the
  same native promise, now this gives if I understand correctly, an easier path towards providing useful debugging experience
  about the promises, so I’m not like saying our API should be a single bit focused, and definitely agree that 
  people are experiencing through- take credit that running them concurrently is a problem it’s like something that’s happening,
  but like when V8 asks us where they should spend their time when improving developer lives in debugging Promises like we want 
  to optimize the common case like what we think most of our users are doing.
* Jordan: If you are only dealing with async functions and the call into other async functions , but many promise APIs
  are not implemented in terms of async functions and a weight is just promise start resolved around the thing you’re awaiting;
  if you don’t provide the way to a way to debug async stacks with regular Promises, then people who are trying to debug their 
  async functions are going to find that a magical and undeterminable subset of their async operations can be stepped through
  in the debugger and the rest cannot. Regular promise chains and async await are so inextricably coupled that if you provide 
  a debugging experience for one and not the other it’s going to be subpar because I agree most developers are typing async await
  at this point.
* Benjamin: Is the limitations severe enough to not spend twenty percent of the time on like eighty percent of the game.
* Showing the benchmarking survey data
* Dan & Ahmad: enterprise users around Promises?
* **Ahmad to reach Michael to talk and sync up next session (list of attendees)**  


## Upcoming Meetings [#74](https://github.com/nodejs/user-feedback/issues/74)

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.


