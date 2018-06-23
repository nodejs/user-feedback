## User Feedback Team Meeting 06-22-2018
## Links

* **Recording**:https://www.youtube.com/watch?v=YbH3k1-Vo6w 
* **GitHub Issue**: #72
* **Minutes Google Doc** https://docs.google.com/document/d/1v9iX6RyCjINL6gbes1bSOVN93-vbxuVvAwzsF83kchI  
* **[General Public Meeting 07.16.2018, 9AM Pacific time](https://github.com/nodejs/user-feedback/issues/74)**

## Present

* Michael Dawson (@mhdawson)
* Dan Shaw (@dshaw)
* Mihai Ene-Pietrosanu (@mihaiep)
* Tierney Cyren(@bnb)

## Agenda
* Public User Feedback request - European General User Feedback at WorkerConf #56
* Invite Node.js tooling ecosystem folks to discuss user feedback #37

## Announcements

* Extracted from **user-feedback-meeting** labelled issues and pull requests from the **nodejs org** prior to the meeting.

### nodejs/user-feedback

* Public User Feedback request - European General User Feedback at WorkerConf [#56](https://github.com/nodejs/user-feedback/issues/56)

  * Doing session similar to one at IBM Index Conf
  * If you have any suggestions of people in Europe, Tierney -> Dan Kahn
  * Dan -> still some management issues in adopting Node.js in Europe, good chance
    that will be part of the discussion.
  * Tierney made a few other suggestions based on the attendee list.
  
  * Mihai, will it be streamed live? If possible would be great. Dan will try to record and setup
    zoom stream.

* Invite Node.js tooling ecosystem folks to discuss user feedback [#37](https://github.com/nodejs/user-feedback/issues/37)

  * Nothing to talk about on this front, just remove label.
  * Happy with progress that Chris is making

* Pull in threads from collab summit.

  * 3-5 people mention, we would like to do sessions, encourage people to create issues but I 
    don’t think they have shown up.
  *  main one that Dan remembers is promises
  *  Tierney suggested that we create issue. 

* Next user-feedback session ?

* Better metrics around real-world usage
  * need to figure out good way to get data
  * go to 3 major cloud vendors who are members to get data?
  * share anonymously, only publish as a total.
  

## Q&A, Other
##  Meeting Notes:
* Dan: I am a week away from worker conf; I will be doing a public session feedback similar with the one at Index 2018.
   Calling for contacts in Austria, Eastern Europe side, to get some connections set up ahead of time.
* Tierney: What about Dan Kahn?
* Michael: Are you going to focus on tooling, enterprise or general?
* Dan: General and European challenges from the discussion I’ve had with other members there; there are still sort of 
  management tensions that folks are dealing with, getting to use the technology, folks are still a little bit more comfortable
  with Java and some other technologies.
* Tierney: There is an individual from Bloomberg, Oracle.
* Mihai: It will be great if we can have this live on Youtube or have the recording audio files and then 
  I will extract some notes.
* Dan: There were some discussions on Berlin summit they did not get in GitHub. I had encouraged people 
  (had discussions in Berlin) to open issues, but the reality there are not issues with them the only one I remember top of mind
  was Promises. Are there any other sessions that folks remember we need to capture?
* Tierney: One thing that I’ll suggest, and this is just from helping bootstrap stuff is take away as much of the big like
  that starting work as you can from other people and let them carry on with it because pulling the trigger on creating 
  an issue it theoretically very simple it’s the largest barrier to entry. So, once you get start doing that and introduce
  that to people it’ll become easier over time.
* Dan: To clarify this your suggestion is to go and create the issue for folks or don’t create the issue and let them basic issue?
* Tierney: Create issue for folks and then make sure they come in and engage with it and you can help manage that a little 
  bit or do whatever we need to do but talking and creating the issue is very helpful to get things going, because people 
  often don’t feel like they are familiar enough so having someone who is perceive is familiar enough, breaks that barrier.
* Michael: On the Promises front the other groups we have are kind of focused around groups in the ecosystem and I could see 
  Promises being a topic that anyone of those groups would look at, I’m looking what would the promises of User Feedback
  group will be? There were a lot of discussion in the previous sessions around use cases, that was almost led as: let’s understand
  the technical requirements and then define requirements and then push that forward.
* Tierney: I think this can be less like ecosystem things that we’ve been doing and more like the first one we did with 
  the benchmarking group, so we kind of do have two approaches, have precedent we’ve just been leaning on the latter approach
  a lot more recently, but that doesn’t mean that we can have a lot more input from different individuals who are in the 
  ecosystem now so we can go do those things more strongly now, those original approaches.
* Michael: And sort of like the benchmark we supported an effort that they came up with and I think similarly I can easily
  see that being the case that there’s bunch of places where actually we have discussions about creating surveys and 
  I’m involved in a couple of those where it’s like as soon as we come with those questions we’ll bring them over to user 
  feedback group to help the community, get that feedback and one of them is around debugging, sort of sub workgroup being 
  created in the diagnostic workgroup, I think they were talking about one , modules we’re also talking about one.
  What in the end do we come out with, that’s the thing we’ve achieved.
* Dan: So my understanding from the sessions, we have very active proponents that have engaged with Promises ecosystem and 
  they feel like the broader community doesn’t have a clear understanding of the scenarios where promises are used and the 
  challenges around that and they’d like to build understanding and get feedback around promise usage and if I put words in 
  their mouth I would think that their end game would be to see if they could influence the project more to encourage more 
  platform level adoption and support for Promises.
* Dan: Speaking of that we need to do at least one session, we’re going to teach you how to fish an then please run more 
  of those sessions so you can get more feedback we will continue to amplify and support, encouraging either companies
  that are actively using promises or companies that are struggling or unhappy with promises, to come and engage in those 
  sessions and by having those sessions captured and the feedback discussions, that will provide the baseline inputs that 
  the project needs to be able to get more feedback and then from there maybe a survey would be a good tool, but I think 
  there’s probably some steps before a survey, some consensus building before a survey to be most effective.
* Michael: In that context make sense, we can only take on so many regular meetings for imprint we’ve got the tooling one 
  is going off on its own cadence which is good the other two we still need to do put some  work into to actually get some 
  critical mass, we should grab benchmarking and say ”what do you think this will help get this off the ground the best and
  help get those first few initial meetings”?
* Tierney: And on top of that we shouldn’t say just we’ve done one meeting with you and go continue with these meetings 
  because it’s very helpful someone who can answer questions like how things work so one of the member of the group will always
  be attending, we don’t have to commit to attending one but raising our hand if we can, that would be helpful and beneficial.
  One of the other things would be useful for feedback, is documentation and this is coming from that redesign in my experience,
  we are beginning to look at how we can continuously improve the documentation, improve guides and there’s amount 
  of issues that are going to be created or have been created to create new guides to address that content and we’re at the 
  point where we are beginning to content create simultaneously with the design happening, so being able to get feedback on 
  the current state of the documentation , but just going to have a survey and I will bring the issue for this.
  Begin to collect the questions in the website redesign repo.
* Michael: Dan do you think there’s any other TSC members that we identified as particularly interested on that front?
* Dan: V8 team is interested and I think we get them to engage there.
* Michael: Check with Anna or Francesca to check with Google. If you are going to open the issue I can help with that.
* Dan: Action item for me create the promise outrage and reach out to both; let’s get Ben also bring additional
  members from TSC of some different perspectives?
* Michael: We should schedule a general or enterprise meeting.
* Dan: June 16th General meeting will work.
* Michael: Dan did you have chance to catch up with Ahmad yet?
* Dan: I’ll be happy to have him push forward and organize the next Enterprise session.
* Tierney: One of the things I brought up in the node foundation marketing committee meeting: try to figure it out how 
  we can get better metrics around real world usage of node. How we can do? We need to figure it out some approach, 
  one of approach to do it is go to the major cloud providers, because we have three of them as members go to each member 
  that is cloud provider ask them to share their metrics anonymously and as a group as a batch, so not publish each
  cloud providers metrics. If we can publish the bash of metrics that will be helpful for us to understand real-world usage.
* Michael: It will be interesting, I can see some reluctance, even if just the total numbers published that potentially 
  leaks   information. What sort of the major winning from that data?
* Tierney: We have a number that is npm users, historically said that is node.js instances, that is not accurate.
* Michael: What’s the problem that it solves?
* Tierney: The problem it solves is we don’t have any understanding of how node is used, we understand the places it’s used,
  we don’t understand at what scale.
* Michael: I think once you go beyond some high-level numbers you then get into even more trickiness in terms of like can
  the cloud providers even collect that data? There is a lot of discussions around it, but you can’t just go and collect
  their data, you got to respect their privacy and what they’re doing. There are a lot of challenges…
* Tierney: Grossly underreporting right now, with 2 data sets we are at the lower end like the nine million number is the 
  lower end of the possible range, so my estimate it’s 18 million.
  We cannot just rely on this data set as the single source truth because even the people who are talking aboutthat single
  source of truth, have their own data sets so we need to be able to co-relate that a bit.
* Michael: Dockers is a good one. The downloads, the docker distros are the other major sources. Are any other ones beyond that?
* Tierney: Public sources, no.
* Michael: Deployments are quite different.
* Tierney: Docker is a closer representation of deployments than downloads because it’s a pull and it’s effectively 
  one person using it, there is zero way to tell if it’s a development deployment or development usage or a CI/CD usage 
  or a production usage.
* Michael: If you want like instances deployed like Kubernetes would probably be very once at the very beginning.
* Tierney: You are deploying once and then things are happening, I don’t know if that should be counted as multiple deployments 
  because you are deploying it and it’s doing that saying.
* Michael: You could think that a cloud provider may pull a docker image once and how is caching to prove.
* Tierney: We do have to begin to try to correlate the data that we have or that data can get and begin to understand
  it and know that are these caveats because that is how we build this platform and that is totally fine. 
  It’s going to be a challenge.

## Upcoming Meetings: 
  * **[2018-07-06 User feedback meeting: Guests: Ben and Ahmad](https://github.com/nodejs/user-feedback/issues/73)**
  * **[2018-07-16 Public User Feedback meeting](https://github.com/nodejs/user-feedback/issues/74)** 

* **Node.js Foundation Calendar**: https://nodejs.org/calendar

Click `+GoogleCalendar` at the bottom right to add to your own Google calendar.

