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
1. Perform a blameless postmortem to figure out what really happened and come up with ideas, so that it doesn't happen again.
1. Schedule practice incident resolution. This is to embed the process in the team and get everyone used to solving problems in a methodical way. 

### Preventing Future Incidents
* Apply monitoring to critical systems for unauthorised changes

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

## Work Center Work Load
Just as important as throttling the release of work is managing the hand-offs between work centers. 
> The wait time for a given resource is the percentage that resource is busy, divided by the percentage that the resource is idle. e.g. 50% utilisation = 50/50 = 1 unit. 90% utilisation = 90/10 = 9 units = 9 times longer! 99% utilisation = 99/1 = 99 times longer!!

A critical part of the Second Way is making wait times visible, so you know when work spends days sitting in a queue, or worse, when it has to go backward, because it is imcomplete or requires rework. 

As the goal is to maximise flow, it is as important to decrease waiting times to reduce the "total process time" of WIP. Often the "touch time" of some WIP is a small fraction of the the total process time, because items are spending a long time waiting to be processed by work centers. 

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

### Organisation
Work Centres are organised into Lanes of Work, which are controlled by Kanban boards. 

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
