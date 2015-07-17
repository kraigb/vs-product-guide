<properties
    pageTitle="Agile Planning"
    description="Planning, tracking, and executing on work is the heart of any agile process, and Visual Studio 2015 continues to make the process more efficient."
    slug="agileplanning"
    order="200"    
    keywords="visual studio, team foundation server, visual studio online, vs2015, vs, visualstudio, tfs, tfs2015, vso, agile planning, kanban boards"
/>

## Access levels and licensing changes

Users with a Basic license to Team Foundation Server have access to Web-based test execution, team rooms, work item chart authoring, and agile portfolio planning tools. This means that all teams of five or fewer members with a "Basic" license have access to these features using the web portal for free, while larger teams can access this functionality at a much lower price point.


## Backlogs
- **Backlog navigation, reordering, and reparenting:** While many teams can work with a flat list of items, sometimes it helps to group related items into a hierarchical structure. For details, see [Organize your backlog]( https://msdn.microsoft.com/Library/vs/alm/work/backlogs/organize-backlog). This includes [team-configurable opt-in to portfolio backlog levels](https://msdn.microsoft.com/Library/vs/alm/work/backlogs/organize-backlog#activate-backlogs).
- **Quick filter of product and portfolio backlogs using keywords:** With the filter textbox on the toolbar, simply type in text from the items you’re looking for and the backlog/result is immediately filtered to show only those items with matching text. This feature helps tremendously when you’re scanning a long backlog or query result for a specific item (or set of items). Note that the matching is done on data in the displayed columns—including tags. On a filtered backlog, then, the context menu provides an option to move an item to the top or to a specific position.


## Task board

- **Show custom-editable fields and tags on cards:** see [Customize cards](https://msdn.microsoft.com/Library/vs/alm/work/customize/customize-cards)for details. 
- **Task board:** bugs as cards: Teams can choose if they want to show bugs on their backlogs, regardless of process template. Teams can also choose to show bugs on the backlogs and task board with requirements (user stories or product backlog items), with tasks, or not at all. See [Show bugs on backlogs and boards](https://msdn.microsoft.com/Library/vs/alm/work/customize/show-bugs-on-backlog) for details.
- **Unparented tasks:** The tasks in the sprint that do not have a parent story show up on the sprint backlog and task board, under an "Un-parented" category. The un-parented row is highlighted with a grey-colored bar. You can move tasks from an un-parented row to any user story, and vice versa. (Note: Drag & drop of an un-parented row is not allowed; it always appear on the top of sprint backlog as well as the task board.) See [Task board](https://msdn.microsoft.com/Library/vs/alm/work/scrum/task-board) for more details.
- **Completed stories:** Completed stories will be collapsed automatically when the task board is opened. All stories on the sprint backlog will be collapsed by default. Stories that are collapsed but have pending work will show a warning on the task board. Collapsed rows on the task board also show the summary of pending work for that user story. And, PBIs on task board appear as cards just as tasks do.


## Work item form and query enhancements
- **Identity selector support for distinct selection and query on identity fields:** The identity control includes a user's full name, avatar, and email address. When you put focus on the control, it starts by giving you an MRU (most recently used) list of people to whom you've most recently assigned work items. If the person you’re after isn't in the list, just click Search and the list will populate with matching results from the users in your account. Many of the places where we display a user's name are also refactored so that it now includes their avatar. You'll see avatars on cards on your work items, boards, and more.
- **Query based on a team's current iteration (Current iteration query token):** This feature gives you the ability to specify a token that represents the current iteration in iteration-based queries. Iterations have dates associated with them, and as you move from iteration to iteration it's very tedious to update all the queries used to track work for the next iteration. This change brings the addition of a new query token, @CurrentIteration, that returns the current iteration based on today's date. Note that there are some limitations with this new token. For example, it doesn't work in Excel. The token relies on understanding your team context, and unfortunately Excel doesn't have all the information needed to determine which iteration is current. For details, see [Query by date or current iteration]( https://msdn.microsoft.com/Library/vs/alm/work/track/query-by-date-or-current-iteration) on MSDN.
- **Quick filter a query using key words** 
- **Query progressive disclosure:** Large query lists are not opened every time the query pane is shown. Only the first two levels are loaded, and then you can load the remaining levels on demand.
- **History control:** The history control has been optimized to make discussions easier to read. Specifically, we’ve reduced the vertical space required so that you can get to the discussions you want to see more quickly, and we’ve done this without reducing functionality.



## Process template enhancements

- **Name change and locked process templates:** The name of the templates has changed from the verbose names that includes the version name (for example, "MSF for Agile Software Development 2013.4") to simply "Scrum", "Agile" and "CMMI". The templates are also locked, which means that you cannot make changes to the shipped templates. To create a custom process template based on a shipped template, simply export an existing template, give it a new name and version, and then reimport it by using the Process Template Manager. Existing projects are unaffected by this change, which means that they can continue to have their process customized by using witadmin.
- **Scaled Agile Framework (SAFe) support:** TFS 2015 provides built-in support for the Scale Agile Framework using our existing Scrum, Agile, and CMMI templates. For details, see the blog post [Scaled Agile Framework Visual Studio Online Process Template Updates](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/15/scaled-agile-framework-visual-studio-online-process-template-updates.aspx).
	- An Epic work item type and a backlog/board can track Epics. Epics are hierarchically above Features. Features are mapped to Epics, like Backlog items are mapped to Features.
	- Full backlog and board functionality means you can manage the Epic backlog like any other backlog as well as customize your Kanban columns and cards to match your needs. (The Epics backlog is not enabled by default. To enable this feature, check the "Epics" checkbox from the Team Settings page.)
	- The Epics backlog can be turned on or off at the team level. As described in our whitepaper, [Scaled Agile Framework: Using TFS to support epics, release trains, and multiple backlogs]( https://msdn.microsoft.com/en-us/library/dn798712.aspx), portfolio teams should enable the Epics backlog. Program and Feature teams can disable the Epics backlog if they don’t manage Epics in your organization.
	- Support for architectural vs. business backlogs: A “Value Area” field is added to all work items that appears on a backlog, that is: Epics, Features, and (depending on your process template), the field also appears on Product Backlog Items, User Stories, and Requirements. The Value area has two values: Business and Architectural. By default value, all Epics, Features, and Stories are Business types. To create an Architectural Epic, Feature, or Story, set the value to Architectural. With this functionality, you can define Architectural Epics, which in turn break down into Architectural Features and Stories, allowing you to track your architectural roadmap across your organization. 
- **Miscellaneous added fields and workflow transitions:** see the comprehensive list on [Changes to process templates](https://msdn.microsoft.com/Library/vs/alm/work/guidance/changes-to-process-templates) on MSDN. 
