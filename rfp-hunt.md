# RFP - Hunt Game

## Statement of Purpose

2020 has turned out to be an interesting year. 
We would like to create an outside, socially-distant game that:

1. Encourages outside activity.
1. Introduces Bearcats to unique and special parts of campus.
1. Supports teamwork, while allowing players to remain safe.
1. Could be an engaging icebreaker for various student organizations. 

## Vision

We would like to create a PWA that can be played on any mobile device. 
The app would encourage players on a team to complete a 'quest' by encountering 
a specific set of locations.

While playing, each player gets one active location from the set of locations in the quest. 

To score that location, the user must enter the geographic area 
(as determined by their mobile device).

Each location is specified by a Latitude (e.g., 40.344085), and Longitude (e.g., -94.880743)
which defines the center of a circle with a radius of 16 feet. 

Each location should have an ordered set of three clues. The first is hardest to guess, the 
third should make it pretty easy to guess. Currently, each clue is a string, but later, each clude may include a photo. 

We will start with a competition that has two teams. Each team has four players. Each quest has four locations. 

When the competition starts, 
1. Each player on a team is randomly assigned one of the locations. 
1. The player the first clue for that lcoation is displayed on the screen. 
1. The player begins moving.  
1. As they get within ___ feet of the location, the background goes (warm color). 
1. As they get within __ feet of the location, the background goes (hot color). 
1. Once within the location, the app celebrates with display and sound & the player earns the location. 
1. If the first clue is not enough, the player can request another clue. 

After scoring their location, 
1. The player should be invited to return to the starting location (show on a map?)
1. The player should return to the start and wait for others to arrive. 
1. All teams scoring all locations earn 100% for the competition (e.g. let each score be worth 25 points for a 100-point competition).

The game is coooperative, not competive and a race to find the location and a race to return "home" provide the competitive aspects. 

## Functional Requirements

Create a progressive web app (or native application) with authentication and 
authorization. The following roles are suggested:

1. Administrator (access to all information including app settings)
1. User (access to their content)

As a user, I want to create a team (serve as captain)

1. The user serves as captain of any team they create. 
1. The captain provides a team name.
1. The captain provides a list of emails of invited members.  
1. A user can accept the team invite and become a team player or reject it. 
1. After three days, if not accepted, assume rejection.

As a user, I want to manage my invites.

1. When I get an invite, I can explicitly decline. 
1. After three days, the invite disappears and my invite declined.
1. When I get an invite, I can accept the invite to join the team.

As a user, I want to design a quest (serve as quest creator)

1. The user serves as designer of any quest they create. 
1. The designer provides a unique quest name among all quests (not just mine).
1. The designer provides a starting location for the quest (Lat, Long, will use default radius)
1. The designer provides a set of four unordered locations for the quest.  
1. For each location, the designer provides location coordinates (Lat, Long, default radius)
1. For each location, the designer provides 3 ordered string clues. (Later a clue may include a photo).

As a user, I want to create a competion (serve as hunt master)

1. The user serves as the hunt master of the competion.
1. The hunt master specifies the start date and time for the competion. 
1. The hunt master specifies the end date and time for the competion. 
1. The hunt master chooses an existing quest for the competion. 
1. The hunt master invites a list of teams to compete about a week before. 
1. Each team captain can accept or reject the invitation. 

As a team captain, I want to manage my competition invites.

1. When I get an invite, I can explicitly decline. 
1. After three days, the invite disappears and my invite declined.
1. When I get an invite, I can accept the invite to join the compeition.

As a player, I want to participate in a competition. 

1. The app will remind me a day before. 
1. On the day of the competition, the app will show the start datetime and the starting location.
1. When the competion starts, I will see the first clue for my randomly-assigned location. 
1. I start moving to the clue.  If unsuccessful, I can request a second clue. 
1. If still unsuccessful, I can request a third and final clue (which should make it pretty easy to be successful). 
1. When I get within __ feet of my location, my display shows (warm color) maybe yellow? 
1. When I get within __ feet of my location, my display shows (hot color) maybe red?
1. When I get within my location circle, my display celebrates and says "Congratulations, you scored!"
1. After celebrating, I am asked to return to the starting location (shown) to wait for the other players to return. 

Security must be addressed throughout the app. 
The app should provide a customizable theme using NW Bearcat colors. 
This theme should be swappable if the app is used at other schools. 

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

Team 

  - Team ID
  - Team Name (unique, 3-25 char)
  - CreatorUserID 
  - datetime created
  - datetime last edited

Player (a player belongs to 0 or more teams)

  - Player ID
  - Team ID
  - User ID
  - Player name (unique, 3-25 char)
  - DateTimeInvited
  - DateTimeAccepted
  - DateTimeRejected
  - DateTimeDeleted?

Quest 

   - Quest ID
   - Quest name CreatorUserID 
   - CreatorUserID 
   - Quest starting location Latitude
   - Quest starting location Longitude
   - date created
   - date last accessed

Location (4 per quest)

   - Location ID
   - Quest ID
   - Location latitude
   - Location longitude
   - Location Value (e.g. 25 points)
 
Clue (3 per location)
 
 - Clue ID
 - Location ID
 - Clue Sort Order
 - Clue string


Competition (many teams completing a quest at given time)

  - Competion name
  - CreatorUserID
  - date created
  - StartDateTime
  - EndDateTime

CompetionTeam mapping

  - CompetionID
  - TeamID
  - DateTimeInvited
  - DateTimeAccepted
  - DateTimeRejected
  - DateTimeDeleted?
  
PlayerScore

- PlayerScoreID
- PlayerID
- LocationID
- DateTimeLocationScored

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

* Module 1: Rapid architecture/data/UI design & proposal competition (~2)
* Module 2: Synthesis of design and initial planning (~2)
* Module 3-6: Implementation iterations
* Module 7: Early release and contract finalization (~1)

## Project Conception and Initialization

Module 1 will include the rapid development of a proposal 
to be presented in Markdown or HTML with in-line images and tables (not Word).

This is quick - occuring at the very beginning of the semester.

This forces hard decisions about entities, screens, and functionality. 
Good effort this this phase will 
make the rest of the project much more effective. 

The proposal should include the following sections.

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

Module 1 teams will be assigned at random for this initial design competiion. 

These teams will be disbanded at the end of Module 1. 

Module 1 is a friendly competition. The teams and client will 
work together to choose the best parts of each proposal and use this to direct the 
remaining effort. 

## Project Definition and Planning

Based on the information learned from all teams rapid response in Module 1, 
we will reorganize and begin a clear, consolidated design vision in Module 2. 

Module 2 will include the development of a detailed contract 
for this semester's remaining work.  Here is where we decide exactly what 
products will be created and what platforms or technology stacks will be used 
for each instance. 

Designs and plans will be presented in the NW Jira, Markdown or HTML 
with in-line images and tables (not Word).

We recommend different teams try different data stores, 
architecture approaches (e.g.microservices), and frameworks (e.g. Vue or 
Vanilla JavaScript custom components).

Getting data correct first is critical. 

Tasks should include getting client signoff on each UI screen before implementation.  

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

## Profession-Based

Practice real-world contribution skills – this is designed to reward the same things life does:

- Successful outcomes created by a group of contributors
- Valuable contributions by each individual.

## Work Planning

Work during the week. 

1. Class is required on Monday.  This day is critical - do your half day of work outside class on Monday - the team needs to "divide & conquer" and figure out who will do what. Get organized; get started. You'll need 9-12 hours of planned tasks (about 3-12 items on the board) each week. 
1. Class is required on Wednesday – this is another great day to complete another half day of work. As you work, close your Jira tasks.
1. Class is required on Friday – this is another great day to complete another half day of work. Finish up, document, submit, and be proud of your accomplishments. 

## Source

<https://github.com/denisecase/rfp-hunt/blob/master/rfp-hunt.md>
