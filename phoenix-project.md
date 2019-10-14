# Background 
## About "The Phoenix Project"
The Phoenix Project is a book by Gene Kim that describes the troubled software releases of a company called Parts Unlimited, and how Bill Palmer, recently reluctantly promoted to VP of IT Operations, is able to promote change over to stabilise the IT systems, successfully deliver the project and turn around the company's fortunes.

## Incident Resolution
1. Pull together all of the information you know about the issue, e.g.
  * process flowcharts showing information flow
  * symtoms of the problem - what's failing (and how) and what's still working
1. Get a list of everything that's changed since the last-known-good state
1. Provide some workarounds and solutions to the issue, noting strengths and weaknesses.
1. Create a timeline of events working up to the failure.
, so that it doesn't happen again.

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

## Discovering Totality Of Current Work 
Pull together all of the currently in-progress work, along with resources required, expected timeline to complete, prioritisation, deadline and impacts etc so that resourcing and a schedule can be worked out.
This shows: 
* Large number of projects are currently in progress
* Project scale varies from days to years
* Lack of resources and resource conflicts 
* Most critical projects would take a long time to complete even without the competition for resources
* Incident and defect resolution work is taking up 75% of the staffs time. Due to severity of incidents, it takes priority over other, scheduled work.
* Proritisation of work is down to the person, and often they are leant on or favours asked to prioritize certain work items, and do additional unplanned work.
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

The number of changes submitted was massive. This meant that although they couldn't pre-authorise some of the changes, they allowed them to le made for a day or two until they could catch up, to prevent loss of support for the new procedure. 

# Workflow Management
Work in progress (WIP) is one of the root causes for chronic due-date problems, quality issues and expiditers having to re-juggle priorities every day. Without control of 'job' and 'material' release, you can't control WIP. 

There are three (scientifically grounded) management movements:
* the Theory of Constraints (ToC)
* Lean Production (Lean) (a.k.a. Toyota Production System) 
* Total Quality Management (TQM)
These are rolled up into The Three Ways:
* First Way - create fast flow of work
* Second Way - shorten and amplify feedback loops to create quality at source and reduce defects
* Third Way - culture that fosters experimentation, learning from failure, understanding repetition and practice are the key to mastery. 

> The goal is to ensure the fast, predictable and uninterrupted flow of planned work that delivers value to the business while minimising the impact and disruption of unplanned work, so you can provide stable, predictable and secure IT services. 

Work should be released depending on how quickly the bottleneck resource can consume work. Improvements anywhere outside the bottleneck are an Illusion (ToC). 

# What is "Work"?
Four types of work:
* Business Project work
