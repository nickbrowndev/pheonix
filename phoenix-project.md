# Background 
## About "The Phoenix Project"
The Phoenix Project is a book by Gene Kim that describes the troubled software releases of a company called Parts Unlimited, and how Bill Palmer, recently reluctantly promoted to VP of IT Operations, is able to promote change over to stabilise the IT systems, successfully deliver the project and turn around the company's fortunes.

## Current Company Culture 
Teams and people move between different tasks depending on immediate priorty and who is shouting loudest. People feel the processes in place are bureaucratic and slow, so work around them. Change Management and Ticketing systems are not used, or teams work on their own system locally. Attempts to enforce the existing (designed by a team of consultants) change process across all of the teams has been tried before but fizzled out due to it being excessively time consuming
No sight of all the work currently in progress across all of the teams, and its prioritisation, resources, status, which causes additional load on already overloaded resources. Results in conflict for resources without knowing what other priorities are.
Delays in performing work cause changes to be rushed last minute to meet deadlines. Processes are worked around to make things happen and problematic changes are made urgently that turn out not to be necessary. Changes are often made straight into Production.
Additional work falls out of the woodwork, causing even more pressure on tight schedules.
Lack of investment in testing environment causes changes to be made without adequate testing.
Software and firmware is many versions out of date. Attemping upgrading causes P1 Prodution outage. Preventative maintenance is not performed, caused by slow processes is Procurement, leading to further outages.
No planned releases, releases from different teams are not tested together and cause issues. 
Testing and deployment time is compressed as software development overruns, and the release date is not moved. Massive efforts are made to hit the release date.
Insufficient communication between teams for handoffs causing issues, delays and finger pointing, as well as issues with the release.
Development of their major project is far behind schedule and overbudget, with additional developers brought on board to attempt to meet current deadline. Critical path tasks aren't being finished out, because of resource utilisation and people having multiple priorities.
Single people are critical to keep multiple things progressing, and bottleneck the performance due to being so in demand.
Due to amount of current work, and firefighting current issues, future planning and design falls by the wayside. Status is not really known, and work (primarily testing) is being deferred due to time limitations.
Turn around time of supporting teams is excessively long.

# Resolutions and Procudures
## Incident Resolution
### On an Incident Occurring
* Create lines of communication between the team (chat room, conference phone etc) and meet frequently to discuss issue
* Arrange for status updates to be sent out regularly (e.g. hourly).

### Resolving the Incident
1. Pull together all of the information you know about the issue, and present it to the team e.g.
  * process flowcharts showing information flow
  * symtoms of the problem - what's failing (and how) and what's still working
1. Get a list of everything that's changed since the last-known-good state. This should be close at hand, from the work tracking system. 
1. Create a timeline of events working up to the failure.
1. Generate hypotheses for the issue (backed up with facts), and receive suggestions about some workarounds and solutions to the issue, noting strengths and weaknesses. Everyone must discuss changes they are thinking about, and no change should be made without agreement. 
1. Review the hypotheses and assign people to lead the investigation into each of the most likely causes. 
1. Once the solution is known, plan a path to resolution, and notify the necessary people about the plan and ETC. 
1. Build a list of possible issues that may occur if the resolution was hastily done or temporary, and communicate this with the necessary parties. Also include details on how to report further issues. 
1. When the fix is deployed, ensure there is standby cover for any further issues for a time. 

### Preventing Future Incidents
1. Perform a blameless postmortem to figure out what really happened and come up with ideas, so that it doesn't happen again.
1. Schedule practice incident resolution. This is to embed the process in the team and get everyone used to solving problems in a methodical way. 
1. Apply monitoring to critical systems for unauthorised changes
1. Investigate how production vulnerabilities occurred in the first place, so that they can be prevented from happening again. 

## Discovering Totality Of Current Work 
Pull together all of the currently in-progress work, along with resources required, expected timeline to complete, prioritisation, deadline and impacts etc so that resourcing and a schedule can be worked out.
This shows: 
* Large number of projects are currently in progress
* Project scale varies from days to years
* Lack of resources and resource conflicts 
* Most critical projects would take a long time to complete even without the competition for resources
* Incident and defect resolution work is taking up 75% of the staffs time. Due to severity of incidents, it takes priority over other, scheduled work.
* Proritisation of work is down to the person, and often they are leant on or favours asked to prioritize certain work items, and do additional unplanned work. Prioritisation direction needs to come from the management, and understanding the tradeoffs required. 
It also indicates where the departments are understaffed, and where additional resources need to be brought in.

## Restarting the Change Management Process
The CM process as designed has several flaws that mean that people don't want to use it
* Lots of mandatory fields
* Outdated information means can't enter correct information
* Maintenance of information is not done because of lack of resources
* Fields are too small or inadequate
* Approvals for work take a long time, and pressure from the business and schedule means that it's not responsive enough
* Fields are used incorrectly (e.g. most things are marked as 'urgent' to get them done)
* Process to approve changes takes a significant amount of time due to discussions about risks and necessity of changes.

In order to get a handle on the upcoming changes, the team use cards and write down the following information:
* Who is planning the change
* The system being changed
* One-sentence summary
The cards are put in a basket, and posted on a calendar to show their intended implementation date.
There is reluctance to drop the previously laid out change process, but it's pointed out that it wasn't being used anyway.

The team agreed upon a definition of a 'change':
> A 'change' is any activity that is physical, logical, or virtual to applications, databases, operating systems, networks, or hardware that could impact services being delivered.

The number of changes submitted was massive. This meant that although they couldn't pre-authorise some of the changes, they allowed them to be made for a day or two until they could catch up, to prevent loss of support for the new procedure. 

### Resource Dependency Planning
Additionally, tasks that require scarce resources or people (environments, people, hardware etc) must be identified at task submission. This prevents work competing for resources to be released into WIP. The tasks that do need competing resources should then identify if a substitute can be used (another person) or be prioritised and scheduled. (ToC). 

### Audit/Security(/Other) Considerations
The systems that are audited, or are security critical or have other implications should be flagged so that work requests submitted to those systems should have additional scrutinisation and any additional tasks required to maintain a good position.

There may be other considerations for outsourcing or sharing work such as storing confidential data, affecting financial reporting etc. This needs to be reviewed so that the work doesn't impact existing commitments. 

## Proritisation Of Changes
Categorise tasks based upon the anticipated impact or risk of the change
### High-risk Tasks 
Those that make changes to risky application, the network or shared databases. List the things that belong in this category. Items in this group must be approved by the board before being scheduled and implemented. 
These changes must have standard procedures to make the changes, such as when they need to be implemented, and what key resources need to be on standby in case there are issues. 
Inform the people requesting these changes on the risks associated
* success rates
* anticipated downtime
as these may cause the change to be withdrawn entirely.
The submitter for these changes has responsibility and accountability for consulting and seeking approval from anyone that could be affected. Then the meeting is just for signing off and scheduling the change. 

### Medium Risk Changes
These are things such as Java Heap Size changes. The submitter for these changes has responsibility and accountability for consulting and seeking approval from anyone that could be affected. Once that's done, the change is reviewed and scheduled. The Board's job is to ensure the process is followed. Keep statistics and note any trends to know whether any changes to the priority need to be made. 

### Standard Changes
Changes that have been done many times before (data uploads etc) that are known to be low-risk should be pre-approved. They still need to be submitted, but can be scheduled independently.

## Reducing Knowledge Dependency Bottlenecks
When a single person contains all of the knowledge about something, they often become a bottleneck. Attempting to fix this bottleneck by adding additional poeple very rarely works, because the bottleneck ultimately helps them all out. 
Often the prioritisation of bottlenecks' work is done by who shouts loudest. 
To resolve this:
* Instruct the bottleneck to only work on assigned tasks. Reject any other tasks that are handed to them. Any other work should be sent to the team lead for handling. 
** It may be that other tasks cannot be completed because they require the resource. This is a planning issue - the tasks need to be released according to the dependencies. 
* Every time the bottleneck fixes the issue, they get a bit smarter and the others get a bit dumber. 

Create a pool of resources to stand in for the bottleneck, to resolve all incidents to closure. They would be responsible for documenting what they had learned, and they would be able to request permission to have access to the bottleneck if required.  The bottleneck would not be involved except for advising, and is not allowed to do anything that can't be documented afterwards. Tickets to the bottleneck should be recorded in the ticketing system for future review and analysis. 

# Workflow Management
Work in progress (WIP) is one of the root causes for chronic due-date problems, quality issues and expiditers having to re-juggle priorities every day. Without control of 'job' and 'material' release, you can't control WIP. 

There are three (scientifically grounded) management movements:
* the Theory of Constraints (ToC)
* Lean Production (Lean) (a.k.a. Toyota Production System) 
* Total Quality Management (TQM)

These are rolled up into The Three Ways:
* First Way - create fast flow of work. 
** Use tools to help with the visual management of the work and its frow through the system. A Kanban board is one of the best ways to achieve this. 
** Look for ways to prevent work entering the system - make sure all work complies with the business objectives. 
* Second Way - shorten and amplify feedback loops to create quality at source and reduce defects. 
** This is key to reducing unplanned work, which kills productivity.
** This is done by
*** creating constant feedback loops from IT Ops into Development
*** designing quality into the product at the earliest stages
*** this must be done by having much faster release schedule 
* Third Way - culture that fosters experimentation, learning from failure, understanding repetition and practice are the key to mastery. 

> The goal is to ensure the fast, predictable and uninterrupted flow of planned work that delivers value to the business while minimising the impact and disruption of unplanned work, so you can provide stable, predictable and secure IT services. 

Work should be released depending on how quickly the bottleneck resource can consume work. Improvements anywhere outside the bottleneck are an Illusion (ToC). 

## Constraints - Increasing the Flow
The first step to increasing flow is recognising your constraints. "The Goal" teaches us that in most plants there are a very small number of resources (personnel, machines, materials) that dictate the output of the entire system. This is the constraint/bottleneck. *Until you create a trusted system to manage the flow of work to the constraint, the constraint is constantly wasted*, which means the constraint is likely being drastically underutilised, and you're not delivering the full capacity you could. It also means you are not paying down technical debt, so your problems and amount of unplanned work continues to increase over time. 

It is critical to protect your constraints in the system so that you can get maximum throughput. 

### Steps to Define Constraints
1. Identify the constraint. Keep challenging yourself to really make sure that it's your organisational constraint, because if you're wrong, no improvement will matter. Any improvement not made at the constraint is just an illusion. 
1. Exploit the constraint. Ensure the constraint is not allowed to waste any time ever. It should never be waiting for resources and it should always be working on the highest priority commitment the team has made to the programme. 
** Reduce reliance on the constraint
** Work out how to exploit the constraint more effectively. 
** Keep eradicating unplanned work. 
1. Subordinate the constraint. In the Theory of Constraints this is typically implemented by something called Drum-Buffer-Rope. 
** A boy-scout troop can only move at a pace dictated by the slowest member. Put the slowest member first to prevent others from going too far ahead. 
** Release all work in accordance to the rate it can be consumed by the constraint. This sets the tempo of work for the organisation.

# Definition of Done
Without a definition of done, one team can 'complete' their work, but may not have achieved everything they need to to hand over the task to the next team. Part of the responsibility for this is determining up-front what a task should achieve, with consideration for the next steps in the process. 

# What is "Work"?
Four types of work:
* Business Project work
* Internal IT Projects
* Changes
* Unplanned Work 
** This is work that prevents you from doing all of the other planned types of work. Unplanned work clears out any planned work because it is typically critically important. 
*** Coordinating changes so they don't fail (and create issues that need resolving)
*** Ensure the orderly handling of incidents and outages to prevent interrupting key resources
***  (waste)
*** It is not free, it is very expensive. Unplanned work is performed at the expense of all other (planned) work.
** It is important to find out where unplanned work is coming from. 
** Unplanned work must be continuously eradicated (in size order) as per The Second Way, but it will always occur (Murphy's Law).
** Unplanned work also prevents proper planning of future work, due to its urgency, so teams end up just reacting. This causes more projects to be piled on, which causes a death spiral. 

## Preventing Unplanned Work
It is important to design in features, and to reduce technical debt to prevent or reduce future unplanned work. 
* Designing for features over stability, security, scalability, manageability, operability, continuity (and all the other 'itties)
* Prevent unanticipated changes to critical systems that may cause unplanned work through monitoring and configuration management.
Non-functional requirements such as these need to be designed into the product at the start, they typically cannot be retrofitted later without significant additional cost. 

## Accepting Work
In a manufacturing plant, they review the order and the bill of materials and routings. Then they look at the loading of the relevant work centers in the plant and decide whether accepting more orders would jeapordise any existing commitments. (i.e. assess capacity and demand). This prevents the need to be scrambling to achieve all of the work, meaning less shortcuts are taken and less unplanned work occurs. 

This is 'technical debt' that's not being paid down. It comes from taking shortcuts, which may make sense is the short-term but the compounding interest of the debt grows over time. If technical debt is not reduced, a team can spend all of its effort paying interest on the debt, in the form of unplanned work.

It is important to be able to realistically assess your capacity and be able say "no" to more work if need be, so that projects can be scheduled and delivered successfully, otherwise work gets done by who shouts loudest. The key to this is knowing the constraints and their loading, and protecting it to prevent any of its time being wasted.

When accepting the work, it is necessary to reconcile the internal and external projects together to find dependencies by linking them together. This will show things such as upgrading a database that is due to be decommissioned. 
Manufacturing Production Control Departments:
* schedule and oversee all of production to ensure they can meet customer demand. 
* when they accept an order, the confirm there's enough capacity and necessary inputs at each required work center, expediting work when necessary. 
* work with the sales manager and plant manager to build a production schedule so that they can deliver on their commitments. 

### Questions to ask about the work. 
In order to make good use of the time available, it is important to weigh up the benefits of each task. 
* Does it increase the flow of project work through the organisation?
* Does it increase operational stability or decrease the time required to detect and recover from outages or security breaches?
* Does it increase the capacity of the bottleneck? 
* What would doing the task do to your project throughput? 
* Does it increase scalability, availability, survivability, sustainability, security, supportability, defensibility of the organisation? 

### Categorising Work
Categorise work according to its importance. Typically this would be done with colour-coding the tasks, so that you can see at a glance what types of work are being performed. 
* Changes supporting important business projects (e.g. top 5)
* Other changes
* Internal improvement projects
* Blocked tasks. 

## Resolving a backlog
To increase control of the system, new work needs to be prevent, and other WIP work needs to be reduced or frozen in order to focus reducing the WIP of the most critical task, and improve performance. 
* Due date performance increases as WIP goes down
* Due date performance decreates as WIP goes up
Even if it means people are less loaded, the waste is in the (invisible) WIP that's stuck in the system at present. 
To get the critical task through, add additional resources where possible to get the work moving. 
This 
* makes people more focussed - less multitasking
* reduces priority conflicts for people

When it comes time to release more work into the system, it should be done by which projects have been categorised as the priorities (e.g. Top 5). Otherwise, it comes down to the workload on the current constraint - i.e. it should be prioritised if it:
* increases the capacity of the constraint, or prevents additional work going to the constraint (unplanned work)
* does not require the constraint
otherwise, it will tie up the constraint and reduce the throughput (improving something anywhere not at the constraint is an illusion). 

When the backlog is resolved some more, additional projects can be released, but the priority should be on the identification of additional projects that will reduce the dependency on the constraint. 

## Prioritisation of Work
It's important to have a set prioritisation of work, otherwise the team members need to figure out their own prioritisation, and this is often based on:
* who shouts loudest at them
* who is most senior
* who treats them well

Prioritisation should depend on the work centers that have capacity to perform the work, along with the resources required to perform the work (Bill of Resources). However, prioritisation should also take into account whether the work will reduce the reliance on constraints in the system. Properly elevating preventative work is at the heart of programs like Total Productive Maintenance, which has been embraced by the Lean community. 
> Improving daily work is even more important than doing daily work. 
The Third Way is all about ensuring that we're continually putting tension into the system, so that we're continually reinforcing habits and improving something. Resilience engineering tells us that we should routinely inject faults into the system, doing them frequently to make them less painful.
Mike Rother says that it almost doesn't matter what you improve, as long as you're improving something? This is because if you're not improving, entropy guarantees that you're actually getting worse, which ensures that there is no path to zero errors, zero work-related incidents, zero loss. This is the _Improvement Kata_.

Katas are repetitious training. Repetition creates habits, habits enable mastery. Doing practice and drills is key to this. Frequent small practice is better than practicing less frequently for longer. To create a culture of improvement, you must create those habits. 

Categorising the work is important when it comes to prioritising the work. 

## Plant Manufacturing
A manufacturing plant is a system. Raw materials start one side and a million things need to go just right for it to leave as finished goods as scheduled on the other side. Everything works togehter. If any work center is warring with the other work centers, especially if Manufacturing is at war with Engineering, every inch of progress will be a struggle.

It's important to stop thinking like a work center supervisor. You need to think bigger, like a plant manager, or better yet as the designer of the plant and its processes. They look at the flow of work, identify the constraints and use every possible technology and bit of process knowledge to ensure work is performed effectively and efficiently. 

In manufacturing, *takt* time is the cycle time to keep up with customer demand. If any operation takes longer than the takt time, you will not be able to keep up with demand. When you can't deliver, it means the cycle time of some critical operation is greater than the takt time, and is the reason for not keeping up with demand. 

To resolve this, a feedback loop needs to be created that goes all the way back to the earliest parts of product definition, design and development - or possibly even earlier. Removal of this constraint is key. 
Examples:
* Toyota re-engineered their hood-stamping machine, preparations and processes to bring the changeover time from three days to 10 minutes. 
* Manufacturing plant combining their painting and curing machines into one machine, eliminating 30 manual error-prone steps, eliminating set up time and achieving single-piece flow. 

This resulted in the following benefits:
* throughput went up dramatically
* when defects were found, they were fixed immediately and other parts of the batch didn't have to be scrapped
* WIP was reduced and work centers didn't overproduce products which sat in the queue of the next work center
* order lead times were cut from a month to a week. 
* stock levels were reduced due to increased agility.

For software, you need to reduce your changeover time and enable faster deployments. Allspaw and Hammond ran the IT Operations and Engineering groups at Flickr. They had worked it up to doing ten deployements a day. They taught us that Dev and Ops working together, along with QA and the business, are a super-tribe that can achieve amazing things. He also knew that until code is in production, no value is being generated, and it's merely WIP stuck in the system. By reducing batch sizes, enabling fast feature flow. This was done by ensuring environments were always available when they were needed. He automated the build and deployment process, recognising that infrastructure could be treated as code, just like the application that Deployment ships. That enabled a one-step environment creation and deployment procedure (just like painting and curing procedure above). 

To realise these benefits, you need to create a deployment pipeline. That's your entire value stream from code check-in to production. You need to get everything in version control. Everything. Not just code, but everything required to build the environment. Then you need to automate the entire environment creation process. You need a deployment pipeline where you can create test and production environments, and then deploy code into them, entirely on demand. That's how you reduce your set-up times and eliminate errors, so you can finally match what-ever rate of change Development sets the tempo at. 

This is to enable business agility, not raw speed. It's about how good you are at detecting and responding to changes in the market and being able to take larger and more calculated risks. 

## Achieving Multiple Deployments Daily
Why would you want to?
* Can deploy small fixes into production
* Can perform A/B testing on features and promotions

What are the benefits
* Tension to reduce the deployment time
* Rapid feedback and agility to respond

### Value Stream Mapping
1. Map out the process that current goes from code check-in to production deployment. This is a "value-stream map".
1. Mark where you have had problems during previous deployments.
1. Add typical time for completion on each of the boxes. 
1. Add a triangle to boxes where work has to wait, to indicate WIP

This indicates that there are two issues at work in a typical deployment phase - "environment"s and "deployment"s
* Environments 
** are not available when need
** considerable rework is required to get them synchronised
** Are typically not synchronised between development, QA, Production etc, nor even between developers. 
** Require a lengthy setting up process for developers. 
* Deployments
** Code packaging process is lengthy and error prone. 
** Knowledge needs to be passed on between software, build manager and release deployment person
** Failures are typically only known when the system is running

Standardising environments in daily use by Dev, QA and Operations means that much of the variance can be removed, resulting in much easier builds. Development builds the exact environment along with the code, and checks that into version control. 

To redesign the process, the right people need to be included up-front. This is like the manufacturing engineering group ensuring that all parts are designed so that they are optimized for manufacturing and that the manufacturing lines are optimized for the parts, ideally in single-piece flow.

Improvements made in the book:
* At the point of check-in, the code gets packaged immediately. When it gets labelled "ready to test", the package is then generated and committed. This starts an automated deployment into the QA environment, and later into the production environment.
* Add someone from security (John) to the start of the process to advise and approve changes, advise on risks and mitigations etc. 

## What is a Work Center?
Work centers are where work is done, and workers support them. When a worker is supporting too many work centers at once they are the constraint, because the work centers cannot then work in parallel.
Work Centers are made up of four things:
* Machine - This is the tools required to complete the task. This can be a type of equipment or in certain circumstances a specific machine. The number of these machines, and the capacity of each determine one constraint. 
* Worker - This is who is required to operatate the machine. The skills of this person determine who is able to perform the work. 
* Method - This needs to be standardised and documented so that other workers can execute it. This will also enable a level of consistence and quality. Documenting of the method (and supporting documentation), or reducing the complexity of the process (e.g. through innovation or automation) will increase the pool of workers who can complete the task, reducing the constraint.
* Measures

For the example of configuring a server:
1. Procurement of the server
1. Installing of the server
1. Configuration of the server to the specification required
1. Validation of the server 

## Work Center Work Load
Just as important as throttling the release of work is managing the hand-offs between work centers. 
> The wait time for a given resource is the percentage that resource is busy, divided by the percentage that the resource is idle. e.g. 50% utilisation = 50/50 = 1 unit. 90% utilisation = 90/10 = 9 units = 9 times longer! 99% utilisation = 99/1 = 99 times longer!!

A critical part of the Second Way is making wait times visible, so you know when work spends days sitting in a queue, or worse, when it has to go backward, because it is imcomplete or requires rework. 

As the goal is to maximise flow, it is as important to decrease waiting times to reduce the "total process time" of WIP. Often the "touch time" of some WIP is a small fraction of the the total process time, because items are spending a long time waiting to be processed by work centers. This is compounded by multiple hand-offs between work centers, if each work center is busy, each hand off is delayed, causing a severe total delay. 

### Organisation
Work Centres are organised into Lanes of Work, which are controlled by Kanban boards. Recurring tasks (such as a deployment) should be organised into individual lanes. 

### Standardisation 
It is important to document and standardise the recurring work to gain mastery over it. This also helps to enforce uniformity between results, leading to greater knowledge sharing (avoiding the 'snowflake' problem of bespoke configurations), and can reduce dependencies on specific resources (the only ones that know specific things). 

Work on identifying and standardising the most frequently recurring tasks (e.g. top 20). 

If flow of work is an issue, assign someone a new role, a combination of project manager and expiditer that helps critical work to be pushed through work centers. They will wait at the work center until the work is completed. This is analogous to the 'water spider' role in manufacturing plants. This prevents important work being held in queues or handoffs. This is only a temporary role, project processes should handle this in normal situations. 

### Reduce Work Center Work Load to Increase Throughput
What the result of this loading on Work Centers means, is that to reduce the wait time you need to reduce the loading on Work Centers. High work center loading causes long wait delays for a task to be completed. 

## Applying Kanban to Key Resources
Using a Kanban board to control the work that key resources complete can help the work get done faster by limiting the work-in-progress. It also helps to predict lead times for work and get faster throughput. It also gives better visibility of the workflow and tracking. 
For the most frequent service requests:
* Document what the steps are to complete them (these should obviously be revised if necessary once issues occur).
* Determine what resources are needed 
* Time how long each operation takes. 
To reduce time, review each of the steps to either reduce the reliance on resources, re-order, or improve time. In order improve the quality of work, add checklists - especially between hand-offs - in order to reduce error rates. 

## Improvement Katas
Implement a two-week improvement cycle, and during each one implement one small Plan-Do-Check-Act project. 

Allocate 20% of time towards improvement projects. 

### Bill of Materials and Bill of Resources
In order to prioritise work, it is important to define these
#### Bill of Materials
Catalogue of all the prerequisits for completing the work. e.g.
* Laptop model numbers
* Specifications of user information
* Software and Licences needed, along with their configurations
* Version information
* Security Requirements
* Capacity Requirements
* Continuity Requirements 
* etc... 

### Bill of Resources
This is the Bill of Materials along with:
* required work centers 
* work center routing

This will allow you to get a handle on what your capacity and demand is. That will enable you to know whether you can accept new work and be able to schedule the work. 

# Identifying Flow of Work
Understanding the flow of work is critical to achieving The First Way. This is about identifying the Work Centers that are the constraints in your organisation.

# Observing the Flow of Work
Work should only go in one direction - forward. When work is going backwards, it means waste. This might be because of defects, lack of specification or rework. When work flows backwards, it typically isn't well documented, which means that it isn't reproduceable and this situation will get worse over time as speed increases. This is a non-value add activity (waste).

The goal is single-piece flow. In any system of work, the theoretical ideal is a single-piece flow, which maximises throughput and minimises variance. To get there you must reduce batch sizes. 

> You'll never hit the target you're aiming at if you can fire the cannon only once every nine months. Stop thinking about Civil-War era cannon, start thinking antiaircraft guns. 

Deployments are still done as if they are physical servers. "As Goldratt would say, you've deployed an amazing technology but because you haven't actually changed the way you work, you haven't actually dimininshed a limitation."

An inevitable consequence of long release cycles is that you'll never hit the internal rate of return targets, once you factor in the cost of labour. You must have faster cycle times. To get there, you must put your constraint 'at the front' like the line of Scouts. 

In the book the folks deployed a SWAT team to address important features without the overhead/baggage of the main product. 

## Tackling techinical debt
1. Identify the top areas of technical debt
1. Tackle them in order to reduce the amount of unplanned work in the system. 

# Cultural Change
It is important to reinforce a culture of operational rigor and discipline, in order for this process to work.

# Personal Work Priorities
1. Provider
1. Parent
1. Spouse
1. Change Agent

# Audit Controls
https://itrevolution.com/audit-101-for-devops-resource-guide-for-the-phoenix-project-part-3-correctly-scoping-it-using-gait-and-gait-r/
> GAIT - Generally Accepted IT Principles
The findings of the Audit were mostly covered by the business processes that were already in place in the company, rather than by additional controls added to the IT. 

Audit and security concerns have to be managed at a company level, so that processes and controls that contribute to the security can be put in place, resulting in a strategy that's not just based around IT solutions. 

# Understanding the Financial Business
Having a meeting with the one of the Financial Executives of the company to understand what makes them tick
* What do you do at this company?
* What differentiates a good day from a bad day for you?
* What are you goals, objectives and measurements for this year?

## Financial Goals
* Health of company
* Revenue
* Market share
* Average order size
* Profitability
* Return on assets
* Health of Finance
* Order to cash cycle
* Accounts receivable
* Accurate and timely financial reporting
* Borrowing costs

While the financial goals are important, they're not the most important. The company can hit its financial targets but still fail. The best accounts team can't prevent failure if the company is in the wrong market with the wrong product strategy and can't deliver a product (IT). 

This goes back to the first way - Systems Thinking - always confirming that the entire organisation achieves its goal, not just one part of it. 

## Company Goals
There are also goals thath the company has as a whole. 
* Are we competitive?
* Understanding customer needs and wants: Do we know what to build?
* Product portfolio: Do we have the right products?
* R&D effectiveness: Can we build it effectively?
* Time to market: Can we ship it soon enough to matter?
* Sales pipeline: Can we convert products to interested prospects?
* Are we effective?
* Customer on-time delivery: Are customers getting what we promised them?
* Customer retention: Are we gaining or losing customers?
* Sales forecast accuracy: Can we factor this into our sales planning process?

Ask which of these measurements are most at risk?

Taking these company goals and feeding them back to the lower teams is important to show them how they can help achieve them, and focus work in advancing them. These initiatives often have people responsible for managing them, it's worthwhile talking to them also to find out:
* What their exact roles are
* What business processes underpin their goals
* List of top things that jeapordise those goals

Then it's necessary to understand the value chains required to achieve each of the goals, including the ones that aren't so visible - such as IT. For example, for a delivery company vehicle maintenance is critical, so preventing breakdowns by replacing the oil regularly will help prevent this. This is akin to applying patching and change management policies. This shows how IT risks jeopardise business performance measures, which enables you to make better decisions. 

The KPIs of the company (such as on-time delivery) can be predicted by using forward-looking KPIs (e.g. percentage of vehicles that have had their required oil changes performed). Failure with the forward looking KPIs indicates upcoming failure of company KPIs. 

Most of these objectives usually depend on IT performance. Understanding and making those links clear is important to know why the company is not meeting its goals, and why the IT is often undervalued. This is about understanding the true business context that IT resides in. W. Edwards Deming called this 'appreciation for the system'. 

This is about discovering what really matters in IT. You must discover:
* where you've under-scoped IT - where certain portions of the processes and technology actively jeapordises the achievement of business goals
* where you've over-scoped IT - where there are additinoal controls that are unnecessary as they're being covered elsewhere. 

Once you've built the value chains, assemble concrete examples of how IT issues have jeopardised those goals in the past. 

There are only three internal control objectives
* To gain assurance for reliability of financial reporting
* Compliance with laws and regulations
* Efficiency and effectiveness of operations. 
This is known as the '_COSO Cube_'.

# Learning From Other Departments
It's key to find out what issues they are having. Typically, they are trying to hit the targets given to them by above. They will likely have ideas about how to change what is happening to get a better outcome. This helps to prioritise the work the IT department performs so that it can help its business better - e.g. better reports functionality. 
What does a bad day look like for them? This often highlights their priorities and their dependencies on IT - and what systems are critical for achieving their goals. Also, this shows deficiencies in the current systems, so improvements can be identified to support the goals of the other departments. 
These discussions indicate what systems and processes are critical to meeting the company's goals, and then you can review this to work out if any of the systems need maintenance or upgrading to better support the company. It also shows which functionality in the systems will help to support the company, and not just the end user. 
Because this is all based upon the measures given by the management, they are the most important goals of the company.

## Mitigating Risks
Knowing this, and having identified the business risk for each system, you can work on each of them to identify mitigations for the risks (e.g. schedule maintenance). You then review this with the person to make sure you've identified the right things. 
The operational risks posed by IT need to be managed just like any other business risk - they _are_ business risks. 

Work with the management team to better nail down the risks and mitigations. 

## Leading Performance Indicators
To mitigate these risks, you need to identify and implement leading performance indicators, so that you can know whether you're going to achieve the goals or not, so that appropriate action can be taken. 

## Integral Security
Security should be embedded within teams to share the expertise amongst the team. This enables integration of security into all of the daily work, and not after things are deployed. 

# Seeing the Benefits of these changes
These are the changes noted in the book (but should not be taken as accurate).
* Number of outages down by 2/3rds
* Incident recovery time reduced by half
* Working with a shared understanding of how to help the business win towards the whole company's goals
* Systems and project work starts flowing faster
* Reduction of dependencies on key resources
* Knowledge is shared amongst the team, so that all members can contribute, which helps us fix things faster
* Escalation of incidents is rehearsed, well practiced and performed in an orderly fashion.
* Additional monitoring of infrastructure leads to pre-emptive notification of incidents
* Reduction in the number of projects, due to determining which are unnecessary, and increasing the importance of improvement projects
* Review of incidents leads to hardening of development and deployment processes, gaining confidence that issues will never re-occur. 
* Change management occurs more smoothly, and work flows more easily. 
* People know exactly what they need to be working on, and motivation improves
* Reviewing work travelling backwards leads to better throughput of work
* Less work on the table means things get completed more quickly
* Removed outdated work from the ticketing system, leading to confidence that the work in the system is important and has opportunity to be completed. 
* Given a better idea of the flow of work, more work can be performed concurrently without jamming up the system and impacting existing commitments. 

This is the effect of the First Way:
* curbing the handoffs of defects to downstream work centres
* managing the flow of work 
** - freezing and throttling project releases)
** - reduce WIP by decreasing batch size. This should reduce uplanned recovery work. 
* setting the tempo by our constraints
* understanding what is important vs what is not

This is the effect of the Second Way:
* create 

## Team Practice
Great teams perform best when they practice. 
> Practice creates habits, habits create mastery of any process or skill. 
This creates trust and transparency.
The team did an outage drill bi-weekly. This would lead to much faster resolution time and better outcome for the company. 
