## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# METHODOLOGY

## BRAINSTORM:

1. Think of questions, not answers when brainstorming.
2. (English) Okay, let me make sure I understand ...so you said.
3. Do we not think enough when coding? Do we jump to the first solution without really considering the problem, without
   trying to analyze and decompose it and understand the components and orthogonal forces involved? Is that the cause of
   bad code (together with time press) and the reason why we typically see a “patch evolution” rather than evolution of
   design?
4. I usually do some research about existing technology based on following criteria: stability, usability, easy to learn
   for new people and easy to share knowledge, price (as there are always budget limits. is it value for money?
   Maintenance cost ? Support cost?), compatibility with existing system, how mature and is it maintenance stage or is
   it, documentation, API, Support (is it community, is support must be purchased, how author response to improvement
   request). When best (or top 3 ) x are selected, then is good to do some prototype and write some learning test to see
   how they meet expectations. We can reuse these tests later to see is changes in third party API didn't break
   anything.
5. Make problem simple, because a simple problem is easier to solve.“If you can’t explain it simply, you don’t
   understand it enough.” - Albert Einstein/Richard Feynman. Explain it as if you are teaching it. Study it more when
   you get stuck — keep resolving the problem until you can explain it. Simplify and use analogies — relate it to things
   people already understand.

## CODE REVIEW:

1. Code review is not testing and you shouldn't tell what to review.
2. If those reviewers cannot solve the issues amicably, then the best thing to do is to have a chat with the whole team.
3. You should spend up to 60 minutes on code review in one session because after an hour you’ll simply grow tired of the
   task and won’t be as efficient in finding errors and defects. Reduce Interruptions with code review
4. How much time should you actually assign to each review? 60 minutes is a good, round number that you should focus on.
   Also, after an hour you’ll simply grow tired of the task and won’t be as efficient in finding errors and defects.
5. I am always striving to improve my effectiveness at work. I much prefer receiving any feedback directly
6. Divide the review into time slots.
7. Don’t try to review the whole project at once. Experts advise not to review more than 400 lines of code at once.
8. Stay positive. Code review can sometimes put a strain on the relationships within the team. Nobody likes to be
   criticised, so it’s very important to keep a friendly atmosphere unless you want your coworkers to lose their
   motivation. Instead of perceiving each and every bug negatively, think positively, as they are the new opportunities
   for improving the code quality in general.
    - (Reason : humans cannot effectively process that amount of information, especially over such a long period of
      time.)
9. To find bugs To check for potential performance or security problems To ensure readable code To verify the
   functionality does what was required To make sure the design is sound Who resolves differences of opinion? Reviews
   may have more than one reviewer. If different reviewers have conflicting advice, how does the author resolve this?
   Pair programming is a form of code review. A review could be simply pulling aside a colleague and walking through
   your code with them. Reviews might be done by checking out a branch and making comments in a document, and email or a
   chat channeMake sure to advocate for yourself and clearly state the progress you’ve made in the past week, which
   goals you’ve surpassed and which projects you’ve led.

## CONTINUOUS INTEGRATION/DELIVERY:

1. Continue Delivery is about built the right thing and put changes quickly. Successfully implemented REDUCE THE COST,
   TIME and RISK of delivering INCREMENTAL CHANGES to users.
2. The software is always releasable on demand. If is any problem with this process, then work must prioritize keeping
   system releasable over delivery.
3. Continuous integration is a skill not tool.
4. Having Jenkins/Bamboo doesn't mean you do continuous delivery.
5. However, if the ultimate goal, is to get the new feature that the developer writes to production, in a matter of
   hours rather than months or half a year, there was still a need to fill the gap between agile development and CI, and
   actually pushing frequent, small updates to production.

## MEETINGS:

1. Write stuff down. Send an email with meeting notes where include all decisions made and all “I will do this”
   statements. It sounds counterintuitive but it will help build trust even if sounds lack trust and catch unexpected
   misunderstandings.
2. When you made a decision, write down why. It will help you to remember reasons behind the decision. “Why” is more
   important than “what.”
3. It should be one day in the week without Meetings. A Meetingless day (excluding morning standup). Due to distracted
   nature of the meeting, we should have at least 1 day where we can do just work.
4. In invitation we use snippets as a mechanism to share information while preventing information overload.
5. MAKE BIG DECISIONS IN MEETINGS, RATHER THAN IN ASYNCHRONOUS CHATS
6. Don’t make decisions in Slack.
0. Don't default to scheduling a meeting. Collaborate asynchronously before call a meeting.Meet  when is necessary, to discuss and make decisions.
   

## PAIR PROGRAMMING:

1. When you’re pairing, this thinking happens out loud as you argue about the best way to approach the design, the best
   way to test this class, the best way to refactor it. One thing I really struggle with, but as a navigator, it’s
   really important: don’t interrupt the driver’s flow. Resist the temptation to tell the driver there’s a missing
   bracket or semicolon. Resist the urge to tell them what order to fix the compile errors in.
2. Ping-pong pairing: this is where one person writes a failing test, the other makes it pass then writes another
   failing test, back to the first to make this test pass and then write another failing test, and so on and so on… This
   can give a good balance to a pairing session as both developers write test and production code and give a natural
   rhythm preventing any one developer from dominating the driver role.
3. The navigator should be taking copious notes, letting the driver stay hands-on-keyboard typing. If there’s a test
   we’ve spotted we’re missing, an obvious design smell we need to come back to or if there’s a refactoring we should do
   next, write it down.
4. Generally, the person that knows the domain/codebase/problem the best should spend the least time is the driver. If I
   don’t know this code and you’re driving, I’m just gonna sit here watching you type. I can’t really contribute any
   design ideas because you know the domain. I can’t ask questions because it stops you typing. But the other way round:
   I can be busy typing learning the code as I go; while you use your superior knowledge to guide me in the right
   direction.
5. We need help of others because we are limited in what we can see. it's also not as simple as "two people working at a
   single computer"
0. Challenges
   -  Pairing can be exhausting (Taking enough breaks and enough of them)
   -  Intense collaboration can be hard (A conversation at the beginning of your pairing session can help you to understand differences between your styles, and plan to adapt to that. Start your first session with questions like "How do we want to work together?", "How do you prefer to pair?".)
   -  meetings Interruptions by 
   -  interpersonal compatibility
   -  No time for yourself
   -  Honestly. Sharing wha you know and all that you don't know.
0. Benefits
   -  Knowledge Sharing
   -  Reflection
   -  Keeping focus
   -  Code review on-the-go
   -  Two modes of thinking combined
   -  Collective Code Ownership
   -  Fast onboarding of new team members
0. Styles
      - Driver and Navigator 
        These classic pair programming role definitions can be applied in some way or other to many of the approaches to pairing. 
        The Driver is the person at the wheel, i.e. the keyboard. She is focussed on completing the tiny goal at hand, ignoring larger issues for the moment. A driver should always talk through what she is doing while doing it. 
        The Navigator is in the observer position, while the driver is typing. She reviews the code on-the-go, gives directions and shares thoughts. The navigator also has an eye on the larger issues, bugs, and makes notes of potential next steps or obstacles.
      - Ping Pong

This technique embraces Test-Driven Development (TDD) and is perfect when you have a clearly defined task that can be implemented in a test-driven way.

"Ping": Developer A writes a failing test
"Pong": Developer B writes the implementation to make it pass.
Developer B then starts the next "Ping", i.e. the next failing test.
Each "Pong" can also be followed by refactoring the code together, before you move on to the next failing test. This way you follow the "Red - Green - Refactor" approach: Write a failing test (red), make it pass with the minimum necessary means (green), and then refactor.


0.
Pair Development
"Pair Development" is not so much a specific technique to pair, but more of a mindset to have about pairing.

Planning in pair on task:
Planning - what's our goal?

When you first start working on something together, don't jump immediately into the coding. This early stage of a feature's life cycle is a great opportunity to avoid waste. With four eyes on the problem this early on, catching misunderstandings or missing prerequisites can save you a lot of time later.

Understand the problem: Read through the story and play back to each other how you understand it. Clear up open questions or potential misunderstandings with the Product Owner. If you have a Definition of Ready in your team, go through that again and make sure you have everything to get started.
Come up with a solution: Brainstorm what potential solutions for the problem are. You can either do this together, or split up and then present your ideas to each other. This depends on how well-defined the solution already is, but also on your individual styles. Some people like some time to think by themselves, others like talking things through out loud while they are thinking. If one of you is less familiar with the domain or tech, take some time to share the necessary context with each other.
Plan your approach: For the solution you chose, what are the steps you need to take to get there? Is there a specific order of tasks to keep in mind? How will you test this? Ideally, write these steps down, in a shared document or on sticky notes. That will help you keep track of your progress, or when you need to onboard somebody else to help work on the task. Writing this down also simply helps remember what needs to be done - in the moment, we too often underestimate how many things we will have forgotten even as quickly as the next day...
Research and explore
Research and explore

When implementing a feature that requires you to use a technology you are both unfamiliar with, you'll have to do some research and exploration first. This work does not fit into the clean-cut "driver-navigator" or "ping-pong" approaches. E.g., browsing search engine results together on the same screen is usually not very effective.

Here is one way to approach this in pair development mode:

Define a list of questions that you need to answer in order to come up with a suitable solution.
Split up - either divide the questions among you, or try to find answers for the same questions separately. Search the internet or other resources within your organisation to answer a question, or read up on a concept that is new to both of you.
Get back together after a previously agreed upon timebox and discuss and share what you have found.

Here is an example of how using the pomodoro technique looks like in practice.

Decide on what to work on next
Set a timer for 25 minutes, e.g. with the help of the many pomodoro browser extensions - or even a real life tomato shaped kitchen timer...
Do some work without interruptions
Pause work when the timer rings - start with short breaks (5-10 minutes)
After 3 or 4 of these "pomodoros", take a longer break (15–30 minutes)
Use the short breaks to really take a break and tank energy, get some water or coffee, use the bathroom, get some fresh air. Avoid using these short breaks for other work, like writing emails.

Plan the Day
Pairing requires a certain level of scheduling and calendar coordination. If you don't take time to acknowledge and accommodate this, it will come back to haunt you later in the day.

Remote Pairing
When the navigator sees the driver do something "wrong" and wants to comment, wait at least 5 seconds before you say something



## TEAM RULES:

1. Fix crap code immediately or in next iteration because bad code accumulates. If the fix is more than "one liner" or
   not sure about it, chat with your technical/practical leads about it. Why? Because in reality as LeBlanc’s law said:
   Later equals never. it is like with broken window in your home. When you broke, you fix it straight away.
2. ADR architecture decision records. It is a great to track your decision and helps you to make better one in future.
   Each decision contains:
    - Decision made
    - Who
    - Options consider
    - Options rejected
    - Risk introduced
3. Software should be always releasable. It has the highest priority over doing new work. If a software is not
   releasable, we do not add new code. We focus on fix a problem first.
4. Complete each feature before moving on to the next.
5. How can we share our best practices with others?
6. The team should have a half day for learning new things or doing fix/improve thing that matter for them.
7. The pre-live environment is critically important.
8. The idea of a code retreat is to allow programmers to write the perfect code they would write if they had all the
   time and resources in the world. And why is it important? Because after experiencing something, calmly and
   thoroughly, you feel more comfortable integrating it into a daily routine. And so, in the end, we will narrow the gap
   between the code that we write every day and the perfect code. Another principle of running a code retreat is
   teamwork. Your team would be exposed to different thinking processes while also learning to work with your teammates.
9. Email is not the best platform to handle project logistics and materials. Lack of elaborate search and sort features.
   The entire process of emailing can be highly disruptive to your workflow.
10. Threads are overwhelming. For teams that end up spending much of their time corresponding via email, you miss the
    human element. Nuances such as intonation and body language can communicate a lot, but email doesn’t give you much
    of a chance to pick up on that. What’s more is that brainstorming sessions are best done as a group, so you may be
    missing out on ingenuity as well.
11. the idea of the “two-pizza team” rule made famous by Jeff Bezos at Amazon, meaning if you can’t feed a team with two
    pizzas, then the team is too large.
12. PDUs are complete units that own a set of microservices. This helps keep smaller teams focused on specific projects
    and avoids complications that come with having too many hands on one set of microservices.
0. The basic rule of thumb is don’t give feedback without permission first.
0. Every team must have a single ordered queue of tasks.

## COMPANY RULES:

1. The performance-based bonus is counterproductive. If a company has a performance-based bonus, try to reduce harm as
   much as possible like a move from personal to the team . Performance-based bonus is pure evil.
    - Employee reviews are useless. Use quick and quite often 1 to 1 session to get feedback, work on improvement and
      remove independents.
    - Employee first , customer second.
2. You don’t need HR or corporate communications, we have the pub instead (tough luck if you have a family).
3. A broken, dysfunctional organization driven by meeting unhealthy goals and metrics will produce broken, dysfunctional
   systems @ Jimmy Bogard
4. Encouraging people to use sick days for mental health when they need them.
5. 40 days paid vacation per year: True disconnection is fundamental to help people de-stress and recharge.

## TDD:

1. The Golden Rule of Test-Driven Development: Never write new functionality without a failing test.
    - We always watch the test fail before writing the code to make it pass, and check the diagnostic message. If the
      test fails in a way we didn’t expect, we know we’ve misunderstood something or the code is incomplete, so we ﬁx
      that.
2. TDD is a programer technique to writing software. It helps you increase confidence and focus on writing code that
   meet criteria.
    - Write the test first, then write the code that satisfies the test. It leads to less buggy code and better design,
      because when you have to structure code in a testable way, you end up making smaller, simpler functions that have
      fewer dependencies.
    - It clarifies the acceptance criteria for the next piece of work. We have to ask ourselves how we can tell when
      we’re done (design).
3. It gives me the freedom to improve later.
4. Whenever you are tempted to type something into a print statement or a debugger expression, write it as a test
   instead.
5. Levels of Testing. We build a hierarchy of tests to gain confidence on various levels:
    - Acceptance: Does the whole system work?
    - Integration: Does our code work against code we can't change?
    - Unit: Do our objects do the right thing, are they convenient to work with?
6. TDD at the unit level guides us to decompose our system into value types and loosely coupled computational objects.
   The tests give us a good understanding of how each object behaves and how it can be combined with others.
7. Martin also explains that a common mistake in TDD is to end up with a one-to-one correspondence between tests and
   implementation. This could mean there is a single test class per implementation class and a single test method per
   implementation method. The main negative result of this is a tight coupling between tests and implementation, leading
   to code that is difficult to refactor and reason about.

## PROJECT:

1. How to Choose Language/Framework?
2. Validate each of them by their performance, syntax stability, security, development cycle, support, cost.
3. Ship early and often. You could also have eliminated this issue altogether by not shipping a big-bang, all-or-nothing
   project at the end of a year. By doing this, you create an excessively long feedback loop.
4. How to start a new project using TDD approach? We want to start from building a “walking skeleton” that we can deploy
   it into a production-like environment, and then run the tests through the deployed system. Including the deployment
   step in the testing process. It is critical for two reasons. First, this is the sort of error-prone activity that
   should not be done by hand, so we want our scripts to have been thoroughly exercised by the time we have to deploy
   for real. Second, The development team bumps into the rest of the organization and has to learn how it operates
   currently. If it’s going to take six weeks and four signatures to set up a database, we want to know now, not two
   weeks before delivery. To design initial structure, we have to have some understanding of the purpose of the system
   and we need a high-level view of the client’s requirements, both functional and non-functional, to guide our choices.
   The tools we build to implement the “walking skeleton” are there to support this learning process. Deploying and
   testing right from the start of a project forces the team to understand how their system ﬁts into the world. It
   ﬂushes out the “unknown unknowns” technical and organizational risks so they can be addressed while there’s still
   time. Understand problem → Automate Build, Deployment, End to End Tests → TDD cycle. The “walking skeleton” is an
   implementation of the thinnest possible slice of real functionality that we can automatically build, deploy, and test
   end-to-end. For example, for a database-backed web application, a skeleton would show a ﬂat web page with ﬁelds from
   the database.
5. Iteration Zero. In most Agile projects, there’s a ﬁrst stage where the team is doing initial analysis, setting up its
   physical and technical environments, and otherwise getting started. The team isn’t adding much visible functionality
   since almost all the work is infrastructure, so it might not make sense to count this as a conventional iteration for
   scheduling purposes. A common practice is to call this step iteration zero: “iteration” because the team still needs
   to time-box its activities and “zero” because it’s before functional development starts in iteration one. One
   important task for iteration zero is to use the walking skeleton to test-drive the initial architecture.0. Log
   Aggregation,b. Performance Metrics, Distributed Tracing, Health Check
6. Make sure to plan the architecture before doing Agile development.
7. Create a performance test suite for the whole application.
8. The Intended Results of the Project. The best way to monitor this is through tangible metrics that can be tracked
   over time. For example, a 25% reduction in rework
0. Software architecture is the skeleton of a system. It defines how the system has to behave in terms of different
   functional and non-functional requirements. agile movement allows us to welcome changes, even late in the development
   phase. Although we are moving from a rigid development to a more flexible one, software architecture is a part that
   is sensitive to changes due to its nature as a skeleton. A key factor therefore, when following the agile movement,
   is to embrace the notion of a sustainable software architecture – one that enables the expansion of the system to
   happen in a gradual, easy, and maintainable way along with growth of the complexity of the project.Software
   architecture defines the skeleton of the future system. It is not just a diagram with lines and dots, but rather a
   complete set of decisions that govern the development of the system, including the code itself. Every decision made
   is a trade-off and should be carefully considered.

## OTHER:

1. Learning from experience/failures is one the most important aspect of being better. Be careful, the experience can
   teach us to repeat poor behavior and to create bad habits. “The Code Works” isn’t where you stop. It’s where you
   start. When it works, make it better.
2. Life/work balance is important and long hours means burnout.
3. Choose good enough solution over perfect. If it is 80% done, and getting it too perfect is going to take a lot more
   effort, ship it, and fix it later.
4. Always add an email address for technical and security issues on your website to allow users to contact you. Why ?
   Read this story: www.daemonology.net/blog/2014-12-25-when-security-goes-right.html
5. Practice coding every day for at least 30 minutes (1h recommended) without excuses If you skip one day for whatever
   lazy reason then you more likely may skip the following day as well and then give up altogether. Don’t let that
   happen. I did twice and it has a very bad consequence on me for a long time.
6. Read lots of Code. While you do it think about:
    - How would I improve this code?
    - How would I have written that block of code?
7. There are core languages/framework/tools that you use every day. It is a good habit to be up to date with what’s new
   in new versions of these things are released, it’s worth investing the time to learn about them.
8. Programming is a creative art based on logic. Every programmer is different so it codes differently. The output is
   what matters. Always maintain constantly shippable code. Always provide defaults for load things. As soon as u see a
   bug, fix it.
0. When you invastigate what went wrong. why do i want do this ? 5 times\
0. 15-minute coffee & learn sessions
0. The “10 things about you” list
0. Chorei? While the goal of a daily team standup is generally to get status updates on project progress, discuss
   blockers, or distribute the day’s tasks, the Chorei asks for mandatory attendance from all employees for a number of
   different reasons: To get everyone on the same page about the company’s top priorities To share any important
   organization-wide updates. To coordinate on schedules and cross-team collaboration. To repeat the company values or
   vision and unite on those pillars. To state goals or intentions, whether from individuals who want to share or as a
   team To get motivated and excited for the workday ahead.
0. At Trello, we have Slack channels that are work-related or team specific, but we also have channels entirely meant
   for  cute puppy pictures, the latest TV series we’re all watching,
   and even an announcement channel where only urgent, company-wide news is shared.
0. refuse to commit to meetings, appointments, or activities at any set time in any future day. 
   As a result, you can always work on whatever is most important or most interesting, at any time. 
   Want to spend all day writing a research report? Do it!
   Want to spend all day coding? Do it!
   Want to spend all day at the cafe down the street reading a book on personal productivity? Do it!
0. Emails relating to topics that are current working projects or pressing issues go into temporary subfolders of a folder
called Action.Keep three standing email folders: Pending, Review, and Vault.
    - Emails that you know you're going to have to deal with again -- such as emails in which someone is committing
      something to you and you want to be reminded to follow up on it if the person doesn't deliver -- go in Pending.
    - Emails with things you want to read in depth when you have more time, go into Review.
    - Everything else goes into Vault. When your typically boisterous and enthusiastic team starts seeming disengaged,
      it’s time to take a closer look at what’s happening. Every once in a while, sweep through your Action subfolders
      and dump any of them that you can into Vault. make sure email is only used for non-urgent messages—reaching out to
      a vendor, a large memo, or a question that can be answered later this week. this article is very consistent with
      the Zero Bugs policy. Critically, the issue needs to find its way to someone who can get it done.
0. Require an agenda for every meeting (r the purpose of the meeting, who should attend)
   Whenever someone is mentioned in the meeting conversation and they aren't in the room, we'll bring them in. to avoid
   snowball effect with the interpretation of the sentence the rule for all meetings is, “If one person is on a webcam,
   we’re all on a webcam.”

stress detection : Have you noticed that when you’re exceptionally stressed you tend to be a lot more terse with the
people around you? The same is true with your team.

If the flow is more complicated, there should be an algorithm that everybody should agree on. An example may be:

    If there is downtime, it’s the top priority of everyone affected
    If there is an incident, it’s the top priority for an on-call agent
    My deployed issue waiting for my verification
    Reviewed pull request waiting for deployment
    My pull request with completed code review that requested changes
    Outstanding pull request waiting for code review
    Customer escalation received through email. For valid ones, create incident and delegate to on-call. For invalid ones, reply, apologize and provide customer support link
    Top issue in the sprint backlogs
    Any issue in the “when engineers have time” backlog

Bottom line—This culture of gratitude is extremely important to motivate employees to do their best work and have a high
level of job satisfaction.1. Provide Sincere And Consistent Recognition

2.
    2. Give A Thoughtful Gift A common way to show appreciation for your employees or coworkers is to give a physical or
       monetary gift. This is a common ritual in Japanese workplaces. It’s called omiyage.
3. Get Your Team Involved For example, your weekly team meeting can have a 10-minute thanks session in which the floor
   is open for anyone on the team to recognize a colleague for going the extra mile that week. I

Slack/Instant Messaging: As the name implies, instant messaging is for things that should be somewhat instantly
communicated. A quick question or request you’d typically ask someone in the office is something you should defer to
your instant messaging platform.
High-quality software is cheaper to produce
Summing all of this up:

Neglecting internal quality leads to a rapid build-up of cruft
This cruft slows down feature development
Even a great team produces cruft, but by keeping internal quality high, is able to keep it under control
High internal quality keeps cruft to a minimum, allowing a team to add features with less effort, time, and cost.



We will not consider the approach with mocking static methods due to its bad performance reputation.
* If you can do something in five minutes or less, do the thing.
* the best performing teams are ones where individuals feel a sense of belonging and psychological safety.
* team is a group of productivity superstarsChat is the workplace for distributed teams.
* Don’t Rely On Chat Decision-Making
* Being vulnerable involves being honest about what you don’t know, what scares you, and where you need support from others.
* YAGNI — “You Ain’t Gonna Need It”. If you run into a situation where you are asking yourself, “What about adding extra (feature, code, …etc.) ?”, you probably need to re-think it.
* Each attendee should call in from their own computer and have their video turned on
* Give credit where credit is due—always tag the person where work is happening that references them
