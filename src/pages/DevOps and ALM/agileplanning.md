<properties
    pageTitle="Agile Planning Improvements"
    description="Planning, tracking, and executing on work is the heart of any agile process, and we continue to make the process more efficient."
    slug="agileplanning"
    order="200"    
    keywords="visual studio, team foundation server, visual studio online, vs2015, vs, visualstudio, tfs, tfs2015, vso, agile planning, kanban boards"
/>

## Unparented tasks

The tasks in the sprint that do not have a parent story show up on the sprint backlog and task board under an "Un-parented" category. The un-parented row is highlighted with a grey-colored bar. You can move tasks from an un-parented row to any user story, and vice versa. (Note: Drag & drop of an un-parented row is not allowed; it will always appear on the top of sprint backlog as well as the task board.)

## Completed stories

Completed stories are be collapsed automatically when the task board is opened. All stories on the sprint backlog are be collapsed by default. Stories that are collapsed but have pending work show a warning on the task board. Collapsed rows on the task board also show the summary of pending work for that user story, and PBIs on task board appear as cards just as tasks do.

## Text filtering on backlogs & queries

Quickly filter backlogs and query results by using the filter textbox on the toolbar. Simply type in text from the items you’re looking for and the backlog/result is immediately filtered to show only those items with matching text. This feature is really handy when you’re scanning a long backlog or query result for a specific item (or set of items). Note that the matching is done on data in the displayed columns—including tags.

## Re-ordering in a filtered backlog

The context menu provides an option to move an item to the top or to a specific position, even when a filter is applied on the backlog. 

## Taskboard: Bugs as cards

Teams can choose if they want to show bugs on their backlogs, regardless of process template. Teams can also choose to show bugs on the backlogs and taskboard with requirements (user stories or product backlog items), with tasks, or not at all.

## Identity control and avatars

This control includes a user’s full name, avatar, and email address. When you put focus on the control, it starts by giving you an MRU (most recently used) list of people to whom you’ve most recently assigned work items. If the person you’re after isn’t in the list, just click Search and the list will populate with matching results from the users in your account. We've also refactored many of the places where we display a user's name so that it now includes their avatar. You'll see avatars on cards on your work items, boards, and more.

## Current iteration query token

This feature gives you the ability to specify a token that represents the current iteration in iteration-based queries. As you may know, iterations have dates associated with them. As you move from iteration to iteration, it's very tedious to update all the queries used to track work for the next iteration. This update brings the addition of a new query token, @CurrentIteration, that returns the current iteration based on today's date. 

There are some limitations with this new token; however. For example, it doesn’t work in Excel. The token relies on understanding your team context, and unfortunately Excel doesn't have all the information needed to determine which iteration is current. 

Learn more about the [current iteration query token](https://www.visualstudio.com/en-us/news/2015-mar-10-vso).

## Query progressive disclosure

Large query lists are not opened every time the query pane is shown. Only the first two levels are loaded, and then you can load the remaining levels on demand.

## Process Template changes

The name of the templates has changed from the verbose names that includes the version name (for example, "MSF for Agile Software Development 2013.4") to simply "Scrum", "Agile" and "CMMI". The templates are also locked, which means that you cannot make changes to the shipped templates. To create a custom process template based on a shipped template, simply export an existing template, give it a new name and version, and then reimport it by using the Process Template Manager. Existing projects are unaffected by this change, which means that they can continue to have their process customized by using witadmin.


