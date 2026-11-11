---
mode: do
review: delete
review_note: "Every item is crossed out (done). Delete, or move to Archive."
---
QRpe - API Gateway
- sms gateway

Gonzapay - AML
- Setup BigQuery, to consume the data
- 

Context
- currently, logged in as admin, maybe this could be influencing some things mentioned below

~~project management~~
- ~~on login; the user provides an email, let the email be saved so that next time on login, we present the user with an option of continue as, with actions of changing email if that is not the account they want to login as, or request otp if that is the account they want to continue wioth~~
- ~~settings~~ 
	- ~~there is this project I have transfered ownership; but there are some actions that I can still do on it; add member, remove member, edit project, delete project; some of these actions should not be visible to user without permissions such as remove member,~~
	- ~~then for actions like edit project, delete project, add member the action items ie buttons should be displayed but greyed out with a lock icon on the right in the button, on hover - a tooltip i s displayed ; You don't have the right permission to perform this action. Talk to the project lead~~
- ~~work items~~
	- ~~currently; on view only the todo and in-progress items are shown, let also backlog items be displayed~~
- ~~work item drawer;~~ 
	- ~~currently the members are not allowed to perform some actions like editing the state, cycle, milestone, external,... etc but this is implemented only on the back side, but it should also be done on the front ie a user can see badge Todo, but it doesnt trigger the dropdown for it to be updated if they dont have the rights~~
	- ~~then, also on other sections like blocked by, sub-tasks, the ctas ie buttons should not be showed to user who cant do the action~~
	- ~~but for comments, any user can comment~~
- ~~yeah, but of course, users who are assigned will need to update the task item~~
- ~~so certain cta are to be introduced for the user working on the task, and they can still be sed by project lead~~
	- ~~eg when an item has been assigned to user; the assigned user can mark it in progress, then when they are done (sth to be introduced), they mark it as under review so for an action assigned to user; if its in todo; the actions avaialbe on it, are 1) marking it in progress 2) then mark it for review 3) then for lead only, they see an extra one of mark done~~
	- ~~so for an item in progress, when the user finishes the item then ask for review, a badge is shown on the item [Under Review], here there is an action that is now visible to project lead Mark done~~
	- ~~if an item is under review, it can be reviewed positively ie then marked as done or feedback provided, this added as comment and the under review badge is removed and task remains in progress~~
	- ~~then the project lead is the one who can mark it as done~~

~~on the list view~~
- ~~the work items; for the work item the badge should also be displayed on the item on the list view~~
- ~~the actions; on the work item drawer 'Request Review' - is very visible but Mark in progress is not that visible,~~ 
- ~~the assignee can mark the item in progress, but in cse of mistake they cant put it back in todo,~~
- ~~also on the kanban, it works as expected assignee cant just move the item to Done section, but there is no notification displayed to the user as to why its not moved~~
- ~~for the assigned, there is part of "External" - when the user cant update this, it~~ 
