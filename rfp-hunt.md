# RFP - Hunt Game

## Statement of Purpose

2020 has turned out to be an interesting year. 
We would like to create an outside, socially-distant game that:

1. Encourages outside activity.
1. Introduces Bearcats to unique and special parts of campus.
1. Supports teamwork, while allowing players to remain safe.
1. Could be an engaging icebreaker for various student organizations. 

## Vision

We would like to create an app that can be played on a mobile device. 
The app would encourage players to complete a 'quest' by encountering 
a specific list of locations.
A player would activate one of the locations in the quest. 
To score that location, the user must enter the geographic area 
(as determined by their mobile device). 
Locations may be explicitly identified (easier) - or described 
using clues (harder).
The quest may require locations to be accessed in a specific order - or 
in any order as specified by the quest creator. 

Points may be earned for:
- a player reaching a location
- a player completing a quest

Points for each location may be assigned based on the estimated difficulty.

Points for a completed quest may be based on the sum of the location points
earned along with a possible bonus based on locating all points
(a completion bonus) - and/or based on the time to complete the quest as
specified by the quest creator. 

Once created, a quest can be opened up again for different teams or people.
Each instance of a quest should be associated with:

- A start and end datetime.
- A set of participating teams.

## Functional Requirements

Create a progressive web app (or native application) with authentication and 
authorization. The following roles are suggested:

1. Administrator (access to all information including app settings)
1. User (access to their content)

Any user may choose to:

1. Create and manage a team (serve as captain)
1. Create and manage a quest (serve as quest creator)
1. Launch a competition (serve as hunt master)
1. Join a team and participate in a quest (serve as a player)

Any user can choose to create a team. 

1. The user serves as captain of any team they create. 
1. The captain provides a team name.
1. The captain provides a list of emails of invited members.  
1. A user can accept the team invite and become a team player or reject it. 
1. After three days, if not accepted, assume rejection.

Any user can choose to design a quest. 

1. The user serves as designer of any quest they create. 
1. The designer provides a quest name.
1. The designer provides a list of locations for the quest.  
1. For each location, the designer provides a location number. 
1. For each location, the designer provides location coordinates (either by 
   entering numbers OR based on a 10' x 10' square 
  around their current location)

Any user can choose to launch a competion.

1. The user serves as the hunt master of the competion.
1. The hunt master specifies the start date and time for the competion. 
1. The hunt master specifies the end date and time for the competion. 
1. The hunt master chooses an existing quest for the competion. 
1. The hunt master invites a list of teams to compete about a week before. 
1. Each team captain can accept or reject the invitation. 
1. By 24 hours before the competition, if not accepted, assume rejection. 

Security must be addressed throughout the app. 

The app must be able to access geospatial information from the device, 
using either native senors or browser information. 

The app should provide visible and audible feedback for the player 
when the active location is encountered. 

The app should provide visible and audible feedback for the player 
when the active quest is completed. 

The app should be responsive, able to work well on various mobile devices 
from phones to laptops and tablets in various orientations. 

The app should provide a customizable theme using NW Bearcat colors. 
This them should be able to be swapped if the app is used at other schools. 

The app must work on:

- an iPhone SE
- an Android device
- a laptop computer
- an iPad

Expected entites may include:

User 

  - email
  - password
  - username
  - date created
  - date last accessed

Team (a team has 0 or more players)

  - Team Name
  - creator (user serving as team captain)
  - date created
  - date last edited

Player (a player belongs to 0 or more teams)

  - Player nickname
  - Points to a user (a user may play under different nicknames)

TeamPlayer mapping

  - DateInvited
  - DateAcceptedInvite
  - DateRejectedInvite
  - DateLeftTeam

Quest (a quest has 0 or more locations)

   - Quest name
   - designer (user serving as quest designer)
   - date created
   - date last accessed

Location (a location belongs to 0 or more quests)

   - Location number
   - Location clue
   - Location coordinates (~10'x10')

QuestLocation mapping

Competition (many teams completing a quest at given time)

  - Competion name
  - creator (user serving as hunt master)
  - date created
  - start
  - end

CompetionTeam mapping

  - CompetionID
  - TeamID
  - Team score (calculated from player scores)

## Bidder Qualifications

Teams that bid on the RFP must be able to:

1. Specify the project.
1. Discuss and clarify details with our acting client before beginning.
1. Implement functionality within times agreed to in the contract.
1. Use professional tools for collaboration.
1. Use professional tools for project management and tracking. 
1. Communicate professionally in person (as the environment allows).
1. Communicate professionally remotely (as the situation requires).

## Performance Metrics

Teams will be judged on their performance to meet the proposed contract deliverables.


## Schedule (Duration in Weeks)

* Module 1: Rapid architecture/data/UI design & project charter competition (~2)
* Module 2: Synthesis of design and initial planning (~2)
* Module 3-6: Implementation iterations
* Module 7: Early release and contract finalization (~1)

## Project Conception and Initialization

Phase 1 will include the rapid development of a Project Charter 
to be presented in Markdown or HTML with in-line images and tables (not Word).

This is quick - occuring over less than 2 weeks at the very beginning. 

This forces hard decisions about entities, screens, and functionality. 
Good effort this this phase will 
make the rest of the project much more effective. 

Phase 1 should include the following sections.

* Statement of Purpose
* Overview
* Benefits
* Epics / User Stories / Tasks
* Acceptance criteria checklist
* Contract scope / budget / schedule (2 semesters)
* User interface sketches (e.g. Figma or paper)
* Technology stack descriptions
* E-R diagram displayed and described
* Consistent set of sample data in Excel, use one sheet for each entity
* Risks and assumptions

Phase 1 teams will be assigned at random for this initial design competiion. 

These teams will be disbanded at the end of Phase 1. 

Development will begin in Phase 2 and will involve the 
creation of new teams that reflect the types of roles each developer would like
to pursue. 

At the end, we'll have a friendly competition. The teams and client will 
work together to choose the best parts of each and use this to direct the 
remaining effort. 

## Project Definition and Planning

Based on the information learned from all teams rapid response in Phase 1, 
we will reorganize and begin a clear, consolidated design vision in Phase 2. 

Phase 2 will include a friendly competion 
between different stacks or approaches, or the group may decide to 
organize the resources according to different interests. 

Phase 2 will include the development of a detailed contract 
for this semester's remaining work.  
It must be presented in Markdown or HTML 
with in-line images and tables (not Word).

We recommend different teams try different data stores, 
architecture approaches (e.g.microservices), and frameworks (e.g. Vue or 
Vanilla JavaScript custom components).

Getting data and user interface correct FIRST are critical. 

NO WORK MAY begin on any UI until the client and mentor have signed a sketch. 

The contract will specify:

* Purpose
* Overview
* Benefits
* Epics / User Stories / Tasks
* Acceptance criteria checklist
* Functional requirements
* Performance requirements (within range of values)
* Other requirements
* User interface sketches (e.g. Figma or paper)
* E-R diagram
* Sample data
* Stack description (including expected tools, technologies, libraries, more)
* Risks and assumptions
* Deliverable artifacts
* Scope
* Milestones
* Schedule and Iteration Plan
* Budget
* Test plan with requirements
* Bid amount

## Payment, Incentives, and Containment

If contract requirements are met 1 7-day week ahead of schedule 
to the satisfaction of the client, 
students are eligible for a 2.5% bonus (based on the total points possible) 
for the associated deliverable.

## Terms and Conditions

Code and applications should be open-source and 
licensed under the Apache 2.0 license. 

## Evaluation Criteria

The client will provide feedback throughout the development process. 

While the client may ask for a requirement change, 
if granted it would require a modification of the contract 
with commensurate elimination of other requirements. 

This would only be applied it there was a critical change in core functionality.  

Typically, requirements changes will be documented 
and would serve as the basis of a change contract.

1. The user interface will be evaluated on aesthetics 
as well as ability to perform a task.  
1. There will be a single major review of every new interface screen.  
1. Good choices will be made for images/color/sound. 
1. Screen space will be used well.  
1. Controls will have signifiers indicating where and how 
operations/input can occur. 
1. Input will be validated. 
1. Appropriate feedback will be employed.  
1. The interface will avoid requiring multiple clicks for common operations.  
1. Confirmation is not required if an operation is easy to undo.  
1. Confirmation is required for operations that cannot be undone.  
1. Default values will be provided for fields.  
1. Do not loose what has been typed if there are errors.  
1. The app will be ADA compliant. 
1. If specified in the contract, support for internationalization may be required.

Note: Correct functionality is not a requirement change.  

## Source

<https://github.com/denisecase/rfp-hunt/blob/master/rfp-hunt.md>
