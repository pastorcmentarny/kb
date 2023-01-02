## **HONEST WARNING**

Content in this KB is for me ONLY. It contains definitions that explain things in the way that is easiest for me to
understand. I am not the author of these definitions so check resources section for the origin of definitions.

# AGILE

Agile is type of software development method based on interactive and incremental development.

* Deliver working software frequently in short timescale.
* Working software is the primary measure of progress.
* Business people and developers must work together daily throughout the project. As work Business – devlopers
  ,face-to-face conversation is The most efficient to succes.
* Simplicity (KISS principle)

## BACKLOG

1. Backlog should be sorted by priority.
2. Product Owner is a response for the backlog.
3. There is a clear line: before a product backlog item turns into a sprint backlog item the product owner is
   responsible. However, once it moves from one backlog to the other, the development team becomes responsible.

## BUSINESS VALUE

1. Finding business value. Did your monitoring and testing lead to a code update that cut down on help desk tickets by X
   percent? Can you connect your code to strategic company objectives?
2. Alternative way to shows business value is to represent as "cost of delay" to shows how much it will cost company if
   feature will be not delivered.

## DAILY STAND-UP

1. Daily scrum meeting is designed to keep development team informed with what hell is going on and detect any problems
   that.
2. An alternative way of doing standup. Start with the highest priority story on your board for the current sprint. Ask,
   “What happened to move this story closer to done yesterday?” The people who worked on it will answer. Next ask, “What
   impediments are keeping this story from getting done?” Again, the appropriate people will speak up. Finally ask,
   “What are we going to do to get this story done (or close to done) today?” The people already working on it will
   probably jump in. Others, now knowing more about the state of the story and what’s needed to get it done, may also
   offer to contribute. Move to the next highest priority story and repeat. Continue until you reach stories that are
   not started and won’t be started today." by Bob Hartman
3. Never use word fast use straightforward instead.
4. The daily stand-up meeting is not a status reporting meeting. Is something changed in priority?
5. standup is a mechanism for getting feedback,is for a conversation it is not for MANANGMENT or status update There are
   a two ways of doing.

* 45 second per person/pair
* (TODO)The sequence continues from right-to-left, top-to-bottom, people describing what is happening with each of the
  work items, and others chiming in if they can help resolve obstacles. On the side, the team leader is recording the
  raised obstacles on the improvement board.

If conversation gets longer than 1 minute, it should be interupted by scrum master/team leader and taken off line.

In the end scrum master/team leader team leader asks if anyone has anything else to share . (about any event that may
happen)

Everybody who wants/need to know about the day-to-day operation of the project should attend the single daily stand-up
meeting.

### What to say on stand-up

1. What did I accomplish yesterday?
2. What shall I do today?
3. What obstacles are affecting my progress?
4. Announcement to share (I work shorter as I attend meetup and so on.)

## WHAT IS DATE SCRUM?

Date Scrum is an R&D pattern where developers are asked to estimate software project requirements upfront for the
project's entirety. This approach is described as doing Waterfall in sprints.

Instead of an Idea Silo, stand up a separate technical VP or Director of Innovation with product managers, sales staff
and engineers in the same silo, all focused on continuously discovering the right thing that customers really need and
want. The product managers are performing market research to figure out where to find the customers. The sales staff are
developing those customers for the coming product. The engineers are working on discovering and implementing the best
solution. The team discloses its value attempts at the daily stand-up. The sales staff share newly found customers likes
and dislikes. The product managers share new places customers can be found in the market. The engineers share what they
have discovered about the best solution to service those newly discovered markets and customer likes/dislikes. Not only
is the whole team sharing what they've done, but they also share what value attempt they are going to take next. This
exposure of discovery work done and planned by team members causes critically important amplified learning about the
market, customer and solution.

## DEFINITION OF DONE

1. One of the most painful things to define. I think dod should answer these questions:
    - Is met all acceptance criteria from all stakeholders?
    - it ready to be released?
    - Does the code have a reasonable level of all type of required tests?
    - Has the code been reviewed by one other programmer?
2. if you’re feeling the Definition of Done as a contract, you’re doing it wrong. It’s more of a guiding light, giving a
   direction, but the direction can change based on new information.

## ESTIMATES

1. There are many ways to do estimates but I learned one thing. Estimates are forecast, not the commitment! If the
   business treats them as commitment then there will cause lots of troubles for a team.
2. Time-based vs point based. Although, I liked time-based estimate in the beginning because they gave me a nice
   imagination and projection. Unfortunately, time based Estimates are treated as a commitment, not forecast.
3. Estimation of bug fixing is a mistake. Don't estimate bugs. From what I see it causes more problems and disorganized
   sprint. In fact, I never seen this work. I prefer Kanban approach to bug fixes.
4. Points feel more accurate for velocity than time-based approach as time gives a feeling of commitment and performance
   check.
5. One thing which is missing for me is a definition of units we use. For example when you using points system like 1 2
   3 5 8 ...What's definition of 1 and How many points are more less description of 1 day of work.
6. When managers abuse velocity and use it to measure the team members (not even the entire team!), they create schedule
   games and a toxic team environment.
7. Velocity is the amount of accepted work, expressed in measurable units, that the team can accomplish in one
   iteration. the speed at which the team is moving towards the project completion. Comparing Velocities between Teams.
   They cannot be compared on the same scale. comparing velocities between teams don’t offer any meaningful results. Use
   actual days not planned (for example planned was 10 , actual 15 then use 15)

## MANAGER CAN FIT INTO AGILE

1. How can managers help developers to do a better job?
2. Dove: I think as a manager, your responsibility to your engineering team revolves around a handful of principles.
   First, I find the 3 principles from Daniel Pink’s book “Drive" are very applicable to engineers — Autonomy, Mastery,
   and Purpose. I think about these three nearly every day and challenge myself to further empower my team and provide
   them with more autonomy than may be initially comfortable for me. In my opinion, distributed autonomy is the most
   important element to scaling a large team and something that is prized at Skyscanner.
3. The next principle is extreme transparency. One of the constant logical struggles with distributed autonomy is that
   there is fear that individuals won’t make the right decision. Starting from a belief that everyone on my team is
   smart, capable, and rational, then my job is to provide them with all of the information they need to make the best
   decision for the business. Any signs that I’m worried someone won’t make the right decision should be an instant
   trigger that I haven’t given them enough information to make the best decision. I personally opt for extreme
   transparency (e.g. Share everything that’s not illegal and is my information to share) because it’s one less set of
   decisions I need to apply of how to filter the information I share with my team. Now my team is armed with the same
   context I have and is much better positioned to make the best business decisions without needing to check for
   approval.
4. The next principle is understanding details and appreciating complexity. Engineers need to believe that their manager
   understands what they’re doing and understands how hard it is. Investing the time and effort to gain this knowledge
   gives a manager a better handle on what’s going on with their team and builds credibility with their engineers to
   trust that the manager is equipped to properly value their contribution.
5. The last principle I believe is critical for managers is to make mistakes in public. It’s well cited and repeated
   that we learn from failure far more than success. However, as a leader, you need to create an environment where
   mistakes are welcomed as learning opportunities instead of something to be ashamed of. One technique I’ve found is
   particularly helpful for doing this is to take a mistake that I’ve made as a leader and describe them as publicly as
   I can for my team. And then repeat every time I make a mistake. As a leader, this takes a lot of courage to show that
   level of vulnerability, but if you aren’t willing to do it, how can you expect your team to do so? I’ll typically do
   this either through an email update, a blog post, or talk through it at a staff meeting and share the mistake I made,
   why it was a mistake, what I learned, and what I’m working on to avoid making the same mistake again.

## KANBAN GENERAL

1. Kanban focuses on continuous flow guided by the Lean methodology. It has five core principles, which are: visualize
   the workflow, limit work-in-process, manage the flow, make process policies explicit, and improve collaboratively.
2. Change culture from push to pull.
3. The agreed scope is staying within your WIP limit threshold(s).

## LESS

#### More about less can be found here: http://less.works/less/framework/why-less.html

1. In Scrum of Scrums is a Coordination meeting.
2. Less is very simple. Barely sufficient methodology. It is Tailoring up (scaling up) because more you learned from
   retrospective more rules you apply. Tailoring down is an opposite to progress , with Tailoring up .. you start making
   progress from beginning .
3. Sprint planning 1 is 45 minutes or less.
4. 3 learning phases based on Shu Ha Ri:
    - You follow kata.
    - You master kata and ask for the exception.
    - You create kata.

## PLANNING

1. Planning horizon should be no more than 3 months. Don't bother to have longer as it is a waste of time.
2. Sprint Planning example:
    - Define the sprint goal.
    - For example "Add Wifi Support".
    - Decide how much to chew off.
    - Decide which stories to do this sprint.
    - Create tasks for stories.
    - Check how much availability do you have during spring ( It can be Bank Holiday, Holidays, Company Events).
3. Limit amount bugs that are allowed to pick up per week. Why only X amount? Because there are always bugs and the
   customer team always wants them all fixed but one of our major learnings was to set a constant throttle of how much
   time we’d devote to (non-critical) bug fixing.
4. Paper Prototyping: Cheap and quick feedback reduced waste and significantly lowered the cost of change. UX/UI ideas
   were quickly validated and refined by the customer in real-time (thanks to colocation) and only after the customer
   agreed was any code written. The design was emergent.
5. Planning is important because it is cost effective development . “I find that weeks of coding and testing can save me
   hours of planning.” Don’t leave it to “the QA process” to find your errors later. BDD framework then you might have
   the option to consider the automated tests as your actual acceptance tests.
6. Keep regression tests around for up to a year — but most of those will be system-level tests rather than unit tests.
7. Keep unit tests that test key algorithms for which there is a broad, formal, independent oracle of correctness, and
   for which there is ascribable business value.
8. Be humble about what tests can achieve. Tests don’t improve quality: developers do.

## PRODUCT OWNER

1. Product Owner is a response for product vision ,Product Backlog items (CRUD operations) and prioritizes backlog based
   on highest business value, importance, 'improvements' ,maintain and refine backlog all the times ,defining productive
   sprint goals.
2. It must be a one person. The entire organization must respect product owner decisions. If your manager wants you to
   build X, some customers want Y to be fixed, and the development team thinks Z is a great option. This is where
   product vision and strategy come into play. it simply comes down to "Goals Come First, Features Second". A
   stakeholder might have a screaming customer who tells them that X, Y, Z bugs need to be fixed. That's great, but it
   might just be that one customer's problem. A Product Owner should know that another problem which 100 customers are (
   validly) screaming about should be actioned first, even though there isn't an internal stakeholder pushing the
   Product Owner to get it done. In essence, this is the point of having a Product Owner.
3. No one except Product Owner is allowed to tell the Development Team what to do and when.
4. It must be a team player and and diplomat because it should collaborate with business and it solution team.
5. Everybody can help, but PO gets the final call. It mean that your 'manager' can NOT jump into your team and change
   the course of your ship. You'll never be able to be a 'proper' Product Owner if that's the case. A stakeholder might
   have a screaming customer who tells them that X, Y, Z bugs need to be fixed. That's great, but it might just be that
   one customer's problem. A Product Owner should know that another problem which 100 customers are (validly) screaming
   about should be actioned first, even though there isn't an internal stakeholder pushing the Product Owner to get it
   done. In essence, this is the point of having a Product Owner.
6. Creating the product backlog as per the product vision was seen by the stakeholders. It can be demanding because of
   balancing between monitoring work by team and stakeholders and customer facing activities.
7. The product owner should be available whenever needed, to remain present, and share information, knowledge, as well
   as expertise with other team members. Since the PO owns the project on behalf of the stakeholders, he/she has certain
   responsibilities towards them.
8. Absent PO: The product owner is absent most of the sprint and is not available to answer questions of the development
   team. (That creates a micro-waterfall approach for the duration of the

## PRODUCT ROADMAP/VISION

1. What is a Product Roadmap? It is something that takes you from A to B, without describing how you get there. A useful
   Product Roadmap shows the plan for delivering customer value over time. It is the output of the product planning
   process where the following have been established:
    - Target market’s needs, size.
    - Competitive landscape.
    - Industry trends.
    - Organisational goals and vision.
    - Feature and benefits that meet the target market’s needs and time where should go live.
2. A product vision gives us the direction and focuses we need to deliver something, anything, that will ultimately
   solve the problems of a customer segment and deliver value to both your business and to your customer. If it is
   well-crafted and well-communicated, product vision should permeate everything you do, from business models and
   product roadmaps to the stories in your backlog and how you execute them.
3. The product roadmap is a powerful tool to describe how a product is likely to grow, to align the stakeholders, and to
   acquire a budget for developing the product. Goal-oriented roadmap focus on goals or objectives like acquiring
   customers, increasing engagement, and removing technical debt.
4. The spec explains the high-level customer story, why (from a business perspective) we’re addressing this, what we
   hope to achieve, and maybe some notes on suggested implementation (though engineers may take or leave this section at
   their discretion; it’s supposed to be helpful, not prescriptive).
5. Important part of Roadmap is to set expectations about changes, describe context and communicate about these changes.

## RETROSPECTIVE

1. The retrospective is one of the most important parts of the Scrum as Scrum is an Empirical process where you
   constantly change and adapt.
2. Retrospectives are a chance to take a step back and reflect on what you’ve been doing. They’re also a barometer for
   the health of your team in terms of communication, transparency, efficiency, and reactiveness. ‘The Prime Directive’
   of the retrospective is not to find fault or blame but to try to detach personalities from the process (by Norm Kerth
   from Project Retrospectives: A Handbook for Team Review).
3. (Type of retrospective) The starfish. Use five categories: Start Doing, Stop Doing, Keep Doing, More Of, Less Of. The
   subtle differences between the categories help the team to think in a different way.
4. If you want to get an honest idea about the feelings of the team on a certain topic, for instance, code quality, you
   can use an anonymous poll.First, write down the scale on a flip chart. Ex. 1= very bad, 4= very good. Then ask
   everyone to write down a number on a post it that represents their feeling about the topic. Fold it and drop it in a
   hat. Take the sum of all the numbers and divide it by the number of participants. If you did it right, you get a
   number between 1 and 4. Make sure there is no middle number.
5. It is quite effective to visually capture (on a wall/board/chart) the feedback the team and keep updating as it comes
   in. a) Things we are doing well and b) Things we could improve on.
6. A poll. If you want to get an honest idea about the feelings of the team on a certain topic, for instance, code
   quality, you can use an anonymous poll. First, write down the scale on a flip chart. Ex. 1= very bad, 4= very good.
   Then ask everyone to write down a number on a post it that represents their feeling about the topic. Fold it and drop
   it in a hat. Take the sum of all the numbers and divide it by the number of participants. If you did it right, you
   get a number between 1 and 4. This gives you the general feeling about code quality at this time. You can repeat the
   same poll after some time to see if things evolved. A great tip from Kris: Always use an even number as a scale, this
   way everybody has to choose a side, they can’t just stand in the middle.
7. the Vegas rule applies: what is said in the room stays in the room. There is no exception from this rule.
8. The rapid retro agenda:
    - Morning
    - Last actions progress
    - Thank you board. Place when you can praise person,practice, team.
    - Task
        - If I could improve one element of our team/ scrum What it could be ?
        - Vote. U can use for each of them 0, 1 or 3.
        - Everybody Write down 1 solution
    - Discuss solutions.
    - Make this as action.
    - Rules:
        - It something that will improve team.
        - Cannot about specific person.
    - In the retrospective, you can uncover major or recurring security problems.
    - ```#NoRetro```: There is no retrospective as the team believes there is nothing to improve. There is no such thing
      as an Agile Nirvana where everything is just perfect. As people say: Becoming Agile is a journey, not a
      destination.
0. , we often start our conversations sharing good news or gratitude about something.

A retrospective Inspect how the last Sprint went with regards to people, relationships, process, and tools; Identify
what went well and wrong and investigate potential improvements; and, Create a plan for implementing improvements

It should have Action point assign to specific person to supervision progress. Rules - a list of things that team should
follow and focus on daily basis

Retrospective should have agenda that is known in advance.

Potential problems with retrospective

* no agenda
* repeatable formula over and over again.
* not enough time
* not learning from action points from precioua retro; not reviewing them.

What to check on retrospective:
+5 +2 -2 -5

product :

* Are we doing the right stuff at the right time?
* Do we have long term goals and vision for the product?
* How do we measure the value of our product?

architecture:
(TODO)architecture — Do we know how to work with building our architecture? Do we have a vision for it? How often do we
need to refactor the code? Why in that way? Are we using the right technology for the product we’re doing?

development :

* How can we deploy more often into production?
* How is our continuous integration approach?
* How can we share our best practices with others?

process:
?

stakeholders —
(todo)How do we know our stakeholders are content with our work? How can we communicate more efficiently with them?

happiness —
* What are we proud of as a team?

* What is stopping us from being better?

Scrum:

* What are practices that we use have become obsolete?
* What could we experiment with in the next sprint?

## SCRUM MASTER

1. Scrum master is like process owner who is responsible for ensuring Scrum is implemented correctly and works smoothly.
2. He is also response for update the team's definition of done (or write one if they don't have one).
3. It should not maintaining an impediment list. It should focus on remove impediments and distractions that might
   negatively impact the team’s progress or results - by any means necessary!
4. Scrum Master understands Scrum principles, values, and practices, and helps the team to become more efficient at
   delivering quality and valuable software. But all of that couldn’t be possible if the Scrum Master doesn’t involve
   the whole organisation in this learning process.
5. It must have a social network and political power to do and influence changes. Patience, lots of humour, follow
   rule "there is not blame sympathy , empathy".
6. It make sure there is no blame culture. Always look to emphasise positive change. Don’t ask “what sucked?” or “who
   screwed up?” Instead, ask what went well, what was useful, what could we do better?
7. Don’t assign work to team members. Teach them to pull work themselves from the product backlog and collaborate to
   define the sprint plan.
8. Instead of repressing conflict, guide team members through healthy conflict resolution so they become better
   communicators and teammates.
9. Allow the team to make mistakes, then help them learn from their mistakes. Lessons are often better learned from
   failures, than from being protected.
10. As Scrum Master looks at the overall health of a company, should Scrum Master be also a Product Manager or Owner? NO
    is the resounding answer to this question. These two roles are held by different people.
11. Great Scrum Masters courageously expose and encourage teams to explore, the elephants in the room as soon as they
    notice them.

## THE SPRINT REVIEW

1. The Sprint Review is more than just a Demo. The Sprint Review is a place to discuss the marketplace changes, examine
   the completed Sprint as an event, update the release schedule, discuss the Product Backlog and the possible focus for
   the next Sprint. This is where the dialog between the Scrum Team and the stakeholders takes place and feedback on
   product Increments is obtained.
2. The Product Backlog is updated after/during the Sprint Review. The meeting is often attended by end-users. The
   Development Team communicates directly with end-users and stakeholders and gets direct feedback from them. The "Done"
   product is showcased on workstations where the stakeholders can play with the new functionality. Inspect: Sprint,
   Product Backlog, Increment, Marketplace, Budget, Timeline, Capabilities. Adapt: Product Backlog, Release Plan.
3. As a rule of thumb, ask those people to attend whose input you need to validate the latest product increment and move
   the product forward. These are typically your key stakeholders - the people who have an interest in your product and
   who you need to develop and provide the offering. These may include people from marketing, sales, service, and
   support, and other business units depending on your product and organization. Collecting feedback from the right
   people is crucial to make the right product decisions:. Therefore, encourage people to actively participate and share
   their views, ideas, and concerns. Use open-ended questions like, "What do you think about the improvements we made to
   the registration feature?" Try to understand why somebody likes or dislikes the product increment. Receiving feedback
   such as "looks great" may feel good, but it does not offer any new insights. Why does the person like the changes?
   And is there anything that could be improved further? Give all attendees the opportunity to be heard. Appreciate
   their opinions and feedback, even if you disagree or find it difficult to accept them. Remember: the creativity,
   knowledge, and feedback of the stakeholders should help you make the right product decisions and offer the best
   possible product.

At the same time, don't accept that individuals use the meeting to make demands or strike the best possible deal for
themselves or their business units. I remember one Sprint review meeting where a senior stakeholder literally shouted
his demands at the product owner and dev team - which was neither appropriate nor helpful, of course.As the person in
charge of the product, be kind and understanding. But do not let the stakeholders tell you what to do. You own the
product and you must have the final say - otherwise, you don't have enough authority and respect.

## STORY

1. To ensure we give our stakeholders confidence our solution should be: functionally correct, stable and predictable in
   all situations, enough capacity for typical workload and secure.
2. In large teams, it makes sense that you to allow an engineer or designer to choose the top card you feel most able to
   handle instead of to take the top card off the stack.
3. it is good to have etiquette about pick up stories. For example developer should never have assigned more than 2
   cards at a time: 1 major project and 1 minor.
4. Introduce acceptance criteria to agree on how you will check the security of specific user stories.
5. Define requirements just in time to keep product features as relevant as possible.
6. There is a danger of scope creep if stakeholders keep adding functionality to the backlog. This could be encouraged
   by the fixed deadline.
7. Keep story lightweight. if that helps clarify the intent. Capitalized, short (50 chars or less) summary. More
   detailed explanatory text and references to supplementary documentation and details
8. Stories have to specify the business value of the story and be a placeholder for a conversation, not a full-blown
   detailed specification.

### Continuous improvement

Continuous Improvement (CI) is a concept is connected with Kaizen approach which means kai (“change”) zen (“good”) is
“improvement”. It is evolution process rather than revolution.

It is ongoing process :

* to improve product, process , team , relationship and tools
* and adapt to current circumstances and reach the best possible efficiency at the current time.

## OTHER

1. In order to succeed, You need to adapt organization system before start Scrum and Less. The problem with an
   organization is organized. You need change organization before changing scrum.
2. The Developers Team is a cross-functional team composed of Software Crafts(wo)men, UX Designer, Analysts, Testers,
   etc. A cross-functional team has everything needed to create a successful project.
3. For Scrum, the agreed scope is the Sprint Backlog (1 or 2 weeks long).
4. Agile is a set of values defined in Agile Manifesto. This is what it means to be Agile.
5. Scrum is a methodology that helps an organization to BE agile.
6. Scope creep (also called requirement creep, function creep and feature creep) in project management refers to
   uncontrolled changes or continuous growth in a project's scope. This can occur when the scope of a project is not
   properly defined, documented or controlled. It is generally considered harmful.
7. PDCA (plan-do-check-act)
    - Plan: problem's root cause.
    - Do: Develop and implement a solution; decide upon a measurement to gauge its effectiveness.
    - Check: Confirm the results through before-and-after data comparison.
    - Act: Document the results, inform others about process changes and make recommendations for the problem to be
      addressed in the next PDCA cycle.
8. A premature decision is a decision made with suboptimal knowledge.
9. No Process is Universal. It always depends on the context.
0. The annual review is bad. Informal feedback sessions-conversations that take place directly following some
   disappointment in performance seems more likely result in an actual improvement in performance.
0. Product must share a common definition of “Done”.
0. Email is great for communication, but not collaboration. All collaboration should be done by accessible by team tools
   like Jira, Wiki.
0. Meetings must be meaningful. “Is this meeting important to getting your job done?”
0. Don’t estimate software defects.
0. A major factor in your choice of Agile framework/methodology depends on the ‘Reaction Time’ your team needs in order
   to change their currently agreed scope of work.
0. A collaborative & cooperative approach between all stakeholders is essential.
0. Project Manager role is to help solve organizational impediments that can slow the team down.
0. Water-scrum-fall is when I worked for a company that embrace Agile methodologies but was own by the corporation that
   enforces old school waterfall.
0. TechRetrospective where team can focus on ... technology. It is especially useful if team is too small to have own
   software architect.
0. Practice Teams - teams focus on a single skill-set i.e. quality assurance.
0. It is impossible to be agile if
    - the bullshit factor of office politics is high, too many layers of management
    - too many stakeholders - decisions are slow.
    - clarity is low. Clarity: it is often not clear who and what organisation is in control of which decision. Things
      simply take longer.
    - Agile do NOT means deliver fast. It means deliver sustainable, high quality output based on value-driven
      value-driven prioritization.
0. This is NOT way to improve efficiency and doing more work in business value sense.
0. Sprint 0. This step iteration zero: “iteration” because the team still needs to time-box its activities and “zero”
   because it’s before functional development starts in iteration one.
    - Visuals and User Experience
    - Technical Architecture
    - Project Plan
    - A One important task for iteration zero is to use the walking skeleton to test-drive the initial architecture.

Sources:

1. http://martinfowler.com/articles/itsNotJustStandingUp.html

Principle #1: Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.

the customer will be satisfied if the software is perfectly created and delivered. We focus on improving our process, not satisfying the customer. Satisfaction is the consequence, not the primary objective.

Principle #2: Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.

Most Agile teams understand the word "welcome" here as a permission to forget about any requirements management at all.


Principle #3: Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.

Principle #4: Business people and developers must work together daily throughout the project.

Working together means quicker turnarounds in communication not lack or roles and responsibilites.
Working together doesn't mean working without clearly defined rules and processes

Principle #5: Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.

Trust doesn't mean lack of control.
Trust is a great word and concept, but it doesn't replace another equally great word — control. Most Agile teams think that trust means exactly that — complete lack of any validation, verification, responsibility, and control.


Principle #6: The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.

Face-to-face doesn't mean at the same office, especially now.
Face-to-face doesn't mean sitting in the same office.

Principle #7: Working software is the primary measure of progress.

Principle #8: Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.

We must remember that any project is first of all a money burning machine. We must therefore remember that any project is first of all a money burning machine. That's why the team must always measure its burn rate and make sure it's aligned with the amount of business value the team delivers.

Principle #9: Continuous attention to technical excellence and good design enhances agility.

???


Principle #10: Simplicity — the art of maximizing the amount of work not done — is essential.

That's a great rule which most Agile teams don't follow at all. This principle means that our tasks are small and simple enough to make sure they are either doable or cancellable.

Principle #10: Simplicity — the art of maximizing the amount of work not done — is essential.

That's a great rule which most Agile teams don't follow at all. This principle means that our tasks are small and simple enough to make sure they are either doable or cancellable.A simple task is a clearly defined, small, and doable work order.

Principle #11: The best architectures, requirements, and designs emerge from self-organizing teams.

Self-organized doesn't mean un-organized.This rule is often translated as a legalization of anarchy. We don't need any project managers, processes, discipline, rules, or policies — we've got holacracy instead!A self-organizing team is a team that doesn't need any supervision from the outside; a team that has clearly defined roles from the inside; a team with a perfect inner discipline; a team with professional management. Not with the lack of all that.

Principle #12: At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

That's a great principle which is translated into so-called retrospective meetings. They work just fine as long as decisions make the team better. Unfortunately, in most cases, programmers in Agile teams are trying to survive, instead of making their teams more effective. Even though the principle says that the team has to become more effective, those retrospective meetings help programmers to become more effective (read "more secure") in the team.

