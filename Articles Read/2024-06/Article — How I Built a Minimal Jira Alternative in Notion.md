---
id: e4e582ab-43a9-4d7d-86b2-8bf2bdcb5123
site_name: Hulry
author: Rahul Chowdhury
date_published: 2024-06-12
date_saved: 2024-06-12
date_read: 2024-06-22
date_archived: 2024-06-22T11:11:25.000Z
original_url: https://hulry.com/notion-project-tracker/
omnivore_url: https://omnivore.app/me/how-i-built-a-minimal-jira-alternative-in-notion-1900d2d1c79
---

 - Site: Hulry
 - By: Rahul Chowdhury
 - Date published: 2024-06-12
 - Date read: [[2024-06-22]]
 - [Read Original](https://hulry.com/notion-project-tracker/)
 - [Read on Omnivore](https://omnivore.app/me/how-i-built-a-minimal-jira-alternative-in-notion-1900d2d1c79)
 - Tags:  #Productivity 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
![Notion](https://proxy-prod.omnivore-image-cache.app/0x0,sPK_UOF0pygkaoGcgV9KRs899Lw9tEqzl9RO93Ooe8rQ/https://hulry.com/content/images/2024/06/notion-logo-themed.png)

Get this project tracker as a ready-to-use Notion template at the end of this post.

It was mid-May, and I had just started planning my work for the next two and a half months.

There's no logical reason why I was planning for two and a half months other than it was already mid-May and I wanted to prepare for a quarter including May.

Anyway, as I planned in my head, I quickly realised I needed a workspace where I could solidify my plans and keep an eye on how each project progressed over the next 10–11 weeks.

I needed a minimal project tracker.

In this blog post, I'll discuss why I decided to build a project tracker from scratch in Notion, and how you, too, can build one without spending a dime.

Let's start with:

## Why Notion?

It's 2024, and there's no shortage of project management apps in the market.

[Linear](https://linear.app/?ref=hulry.com), [Jira](https://www.atlassian.com/software/jira?ref=hulry.com) and [Asana](https://asana.com/?ref=hulry.com) are powerful apps that address almost every aspect of modern project management.

But, for my projects, I wanted something minimal, easy to use and friendly on my wallet.

Having tolerated Jira for years at the various companies I had worked at, I knew Jira was not what I wanted. It was too clunky, slow and bloated with features I would never touch for my personal project planning.

Linear on the other hand is fast, modern and minimal enough for my needs, but heavy on the wallet. I used Linear to plan and track my progress when writing a book, and it was a joy to use the app.

But, Linear's free plan works for [up to 250 non-archived issues](https://linear.app/docs/billing-and-plans?ref=hulry.com) or tasks in a workspace. While this is generous enough, Linear's task archival mechanism is currently automatic.

This means, that there's no button that I could press to archive a task after it's done. The Linear app would monitor my project's status and automatically archive completed tasks after a certain period as configured in my workspace — the earliest being after a month.

This is enough for small-scale hobby projects, but as you start creating and running multiple large projects, unarchived tasks can pile up to cross the 250-task threshold within a few months.

Then, Linear would cost around **$8/month** for the starter plan.

I might be overestimating my task count here but I didn't want to set up my entire project planning on Linear only to either migrate everything to another app after a month or pay another monthly app subscription fee.

With Linear and Jira out of the running, I turned to Notion to solve this problem.

I was [already using Notion](https://hulry.com/notion-review/) to store materials around my business for a while, so why not leverage what I already use for my project tracking needs?

Notion has all the tools needed to build a minimal project management workspace, and the free plan has no such limits as Linear's. Moreover, I didn't need all the fancy integrations offered by Linear and Jira, so Notion appeared lucrative.

## Learn crazy-useful workflows

Get more alternate yet practical workflows and app tips, in your inbox, every Friday. 100% free.

With Notion as my tool of choice for this task, I proceeded to:

## Visualising the project hierarchy

The basic project structure I needed was to have a list of projects I wanted to work on in the next few months and see how far a project had progressed as I completed tasks from each.

Something like this:

![](https://proxy-prod.omnivore-image-cache.app/1200x443,sizuDf1HIzvY6hNOk6ev83gXQddZi4za0ut4E9W9xbn8/https://hulry.com/content/images/2024/06/notion-project-tracker-overview.png)

But, as discussed in an earlier [blog post on goal gradients](https://hulry.com/goal-gradient-effect/), dividing a project into meaningful milestones increases the probability of finishing it.

Therefore, a milestones feature would be a helpful addition.

This is how it would go:

Each project would contain tasks neatly grouped into relevant milestones.

As I complete each task from a project, I should see the progress of each milestone in the project, and also see an aggregated progress of the project. 

This would help me understand how far I'm on a project milestone, and also identify how much work is left on the overall project.

The project tracker would house multiple projects, giving me a neat dashboard to have a bird's eye view of my ongoing work.

So, with the requirements sorted, it was time to get my hands dirty and build this tracker.

## Starting with the Projects view

The first step was to create a blank page in my Notion workspace to reflect the planning for the current year:

![](https://proxy-prod.omnivore-image-cache.app/1730x572,sMG39Ym79Ks6uEF0My3kge94JQhKAqc9qmXtRAlD2O80/https://hulry.com/content/images/2024/06/notion-yearly-plans-page.png)

Now, since I've divided my year into quarters of work, I wanted the same structure on the yearly plans page.

I created a subpage called **Mid-May to July** to house all the plans for that quarter like this:

![](https://proxy-prod.omnivore-image-cache.app/1740x620,sanOjARYkAlli0sNt650xQn1e6SSHN_lWcGjgICHc0lY/https://hulry.com/content/images/2024/06/notion-mid-may-july-plan-page.png)

In that new page, I added an inline database to store and list all the projects for the quarter:

![](https://proxy-prod.omnivore-image-cache.app/1750x1100,s2EmQECM6RgYFg0cqhD7p-ShRm_an9NXxxwaRVy43FPM/https://hulry.com/content/images/2024/06/notion-may-july-plan-blank-projects-db.png)

Then, I edited the pre-made **Tags** property of the database to a **Select** property with a couple of project priority types:

* **Must Do:** This project is critical and must be completed by the quarter's end.
* **Should Do:** This project is essential, but it's not necessary to finish it this quarter.
* **Can Do:** This project is more of a wishlist and should be done only if I can spare extra time for it without disrupting my critical projects.

![](https://proxy-prod.omnivore-image-cache.app/1450x874,st78GSoiFO4H1z20EN-3bQWHsE3jAD32WTrIDj4yoHRY/https://hulry.com/content/images/2024/06/notion-project-type-property-config.png)

This distinction is crucial because it helps me [identify what to work on now and what to postpone](https://hulry.com/todoist-priority-levels-moscow/).

After sorting the types, I added a new **Date** property to the table to set a timeline for the project:

![](https://proxy-prod.omnivore-image-cache.app/1750x708,sml-fT8UTkFZ1lFU5ZdHaBXQdQ3pW6Pf-2k_sQuPJwjU/https://hulry.com/content/images/2024/06/notion-project-timeline-property.png)

Instead of picking a single completion date here, I picked a date range by toggling the **End Date** switch on the date picker:

![](https://proxy-prod.omnivore-image-cache.app/1250x896,sCfrukTkip9wQj0faSeOi-IX7OVTIOzVQNHqIeSIO03A/https://hulry.com/content/images/2024/06/notion-choosing-end-date-switch.png)

This set a timeline for the project indicating when to start and when to end so that I can visualise each project in a neat timeline view like this:

![](https://proxy-prod.omnivore-image-cache.app/1750x748,sAtpnytT8woa3jRkGtff_-3-I9aCETJASTPdV7bdqmHY/https://hulry.com/content/images/2024/06/notion-projects-timeline-view.png)

Not every project starts and ends at the same time, so visualising the lifecycle of each project and how they overlap with the timings of one another helps [efficiently allocate tasks](https://hulry.com/productive-to-do-list/) from each project into a weekly schedule.

You can create a timeline view for your Projects database by adding a new view and choosing the type **Timeline**:

0:00

 /0:12 

![](https://proxy-prod.omnivore-image-cache.app/0x0,sUNapBkrTcQiv8WkMe0LyOklNG0ITCReRSwOpOrct6mE/https://hulry.com/content/media/2024/06/create-timeline-view-notion_thumb.jpg)

Now:

A project is comprised of individual tasks which make up the overall job to be done.

For listing tasks, I had two options.

Since each item in the Projects database is an individual Notion page, I could add a simple checklist of tasks for each project inside this page:

![](https://proxy-prod.omnivore-image-cache.app/1430x736,sfZsQHsMgSg-4BLlQQx-WTJG7nl18KdyaAszxfF7n4AI/https://hulry.com/content/images/2024/06/notion-simple-page-checklist.png)

However, this format creates a barebones, flat list which I can't use to calculate the progress of the project.

To be able to calculate a project's progress, I needed to be able to count each completed task in the project. For that, I needed to:

## Setup a Tasks database

To store tasks across all projects in my plan, I created another inline database in the same Mid-May to July page with two properties — checkbox and name:

![](https://proxy-prod.omnivore-image-cache.app/1760x720,seKW7YDhvwMIjVbuL6gvyuaY1OF7ed_4Wc5A2mePW2aY/https://hulry.com/content/images/2024/06/notion-tasks-database-overview.png)

The checkbox property indicates whether a task is complete and will help calculate a project's progress.

I now had two databases on my planning page, **Projects** and **Tasks**, but both were independent of each other. I didn't have a way to associate each task with a project and vice-versa.

This is where [Notion's database relations](https://www.notion.so/help/relations-and-rollups?ref=hulry.com) came in handy.

If you're from a technology background, database relations are similar to joining two tables in a SQL database.

In non-technical terms, by creating a relation between two databases, we can link items from one to another and perform various operations.

For example, by linking each task with a project, we could filter the Tasks database to show tasks only for a particular project. We could also count the total number of tasks added to a project, etc.

## Notion tips, delivered

Get more helpful app tips and recommendations, in your inbox, every Friday. 100% free.

To associate a task with a project, I added a **Relation** property to the Tasks database, linking each item to the Projects database:

0:00

 /0:09 

![](https://proxy-prod.omnivore-image-cache.app/0x0,s48rz8Zw6HJWNw4psI1MBQMq6NyfsdCPovFqZl_QwUIA/https://hulry.com/content/media/2024/06/add-relation-notion-database_thumb.jpg)

I also toggled the **Show on Projects** switch to make this relation accessible to the Projects database where I could calculate a project's progress:

![](https://proxy-prod.omnivore-image-cache.app/1370x890,s5eDSKhm-YiLqNZ3-L_tm-LiiqbG7qQCFlaZSpytdy54/https://hulry.com/content/images/2024/06/notion-show-relation-projects-tasks.png)

With the relationship between tasks and projects set up, I assigned each task on my list to a project by clicking the Project cell on a task database item and selecting the project:

![](https://proxy-prod.omnivore-image-cache.app/1630x570,sNvE0OsLvxPQUWFzQPSy7_9IqmcXoeD77LC6plzuWhlQ/https://hulry.com/content/images/2024/06/notion-add-relation-database-item.png)

Like other values in a Notion database, you can drag the bottom-right handle of a cell to copy over its value to the subsequent cells:

![](https://proxy-prod.omnivore-image-cache.app/1680x564,sFjVDFMgfmwCUawlpwunKH1R9LveGjt70dumWO_YQ2gE/https://hulry.com/content/images/2024/06/notion-drag-fill-relation-database.png)

This makes bulk assigning tasks to a project easier.

Once I was done, I had all tasks assigned to their respective projects like this:

![](https://proxy-prod.omnivore-image-cache.app/1634x574,s2zrm4s6tChermIaRDQbQh7WDRL_l0lhccd2c-3mRoVY/https://hulry.com/content/images/2024/06/notion-tasks-projects-relations-overview.png)

Also, since I toggled on the Show on Projects database switch, the Projects database automatically got a new Tasks property showing all assigned tasks:

![](https://proxy-prod.omnivore-image-cache.app/1960x528,sFUI-xSJphhxSMRlMIRS-A7tvKMUoHmJXgLHvSKEXmMs/https://hulry.com/content/images/2024/06/notion-projects-tasks-relation-column.png)

Now:

Both Projects and Tasks were located on the same page, and I could have over a hundred tasks spread across projects. The page could get messy quickly.

To tidy the view, I created a **Toggle Heading 2** on the page and moved the Tasks database under the toggle heading to make it collapsible:

0:00

 /0:07 

![](https://proxy-prod.omnivore-image-cache.app/0x0,stqNYxm269JRWV1-5rlq4tZXPo8lAjCBMfE_QsD5zJ10/https://hulry.com/content/media/2024/06/collapsible-tasks-toggle-heading-notion_thumb.jpg)

Now:

Viewing tasks assigned to each project was still a challenge.

I could add a filter on the Tasks database to only show tasks for a specific project, but the process felt redundant and tedious.

Every time I want to quickly glance at a project's task or mark a task as done, I have to update the filter on the Tasks database to show tasks for a single project.

Since each project item on the Projects database is a full-fledged page, a better approach was to add a table view of the Tasks database on each project page like this:

0:00

 /0:09 

![](https://proxy-prod.omnivore-image-cache.app/0x0,sFKUVzFRy5S1xa32Squk8Er_bMbjMRbZdB7-eIVyuUp0/https://hulry.com/content/media/2024/06/add-table-view-tasks-projects_thumb.jpg)

What we now have is an unfiltered view of all tasks in the database, regardless of which project it's assigned to.

To show tasks relevant to an open project page, we can add a filter to the table view to show tasks only for a project:

![](https://proxy-prod.omnivore-image-cache.app/1576x674,sviyC3A2ETackkU7rFqagB29ZFQ2aBlRUa9zwLNGJvEs/https://hulry.com/content/images/2024/06/notion-filter-tasks-projects-database.png)

With the filter added, we can now see all tasks relevant to a specific project:

![](https://proxy-prod.omnivore-image-cache.app/1540x558,s6COcuJFH90ruAmYuzlS1DZhgItrNV7VwTlWbVrFCBb0/https://hulry.com/content/images/2024/06/notion-filtered-tasks-by-projects-database.png)

This is a handy addition because now, opening a project page would list all tasks related to that project instead of having to tweak filters on a top-level Tasks database repeatedly.

0:00

 /0:05 

![](https://proxy-prod.omnivore-image-cache.app/0x0,so11wrQH0kYNTR4Oe_cRmiF7ARKfZEkHssaVfH3mMqgo/https://hulry.com/content/media/2024/06/filtered-tasks-projects-page_thumb.jpg)

The project tracker was already taking shape and was ready for use.

However, it still lacked a crucial element we discussed earlier — showing a project's progress.

So, the next task was to:

## Automatically calculate a project’s progress

Any decent project tracker can display the progress of an ongoing project.

Without a progress display, it's difficult to estimate where we're at in a project and whether we'll get it done in our estimated time.

Building this feature is feasible since Notion supports showing progress bars in databases.

Now, we could render a progress bar by writing a complex formula to calculate the percentage of tasks left in a project, but thankfully, Notion has a built-in property for this purpose — **Rollup**.

Think of [Rollups as a way to aggregate linked database items](https://www.notion.so/help/relations-and-rollups?ref=hulry.com) into a sum, count and other functions.

For the **Project → Tasks** relation, we could automatically calculate the percentage of unchecked tasks in a project with minimal configuration.

Here's how:

First, I added a new property of type Rollup to the Projects database:

![](https://proxy-prod.omnivore-image-cache.app/1450x686,se5tGGuDNH_f6XPH5w17Dc51Ba5Aj-0xGOi1iRfQm-OU/https://hulry.com/content/images/2024/06/notion-rollup-new-property.png)

Then, I set the relation to use for this rollup to the Tasks relation setup earlier:

![](https://proxy-prod.omnivore-image-cache.app/1412x968,smMK2QwpBWaMWqxSdtIf6rtXL5pzyJZ_U5NdueqBAK-8/https://hulry.com/content/images/2024/06/notion-rollup-by-tasks-relation.png)

This revealed a couple of more options to choose from, such as a property to fetch data from, and how to calculate the retrieved data:

![](https://proxy-prod.omnivore-image-cache.app/1410x978,s5WMVtHOoo6kJgYgsWvT0NA1NYTuNhBJwWN_lZMauxkI/https://hulry.com/content/images/2024/06/notion-rollup-properties.png)

I selected the Status property for calculation:

![](https://proxy-prod.omnivore-image-cache.app/1452x928,s6n9mezE0H0I4nBk29dkxIiMQ6ITTR2pk-t89k2vLcRM/https://hulry.com/content/images/2024/06/notion-rollup-status-property.png)

And chose to calculate the percentage of checked items:

![](https://proxy-prod.omnivore-image-cache.app/1506x948,s9tYhUKrV8Pb_Mr6b1et9dwgYt3Ohal1Df82jNXK1-yk/https://hulry.com/content/images/2024/06/notion-rollup-calculate-percentage-checked.png)

With this setup, I already had a percentage progress in the new Progress column which changed as I checked off a task in the list:

0:00

 /0:05 

![](https://proxy-prod.omnivore-image-cache.app/0x0,sOSchTRu5lBtDTYGPfGXGcgeJKn170k5akAcSDdQMCpc/https://hulry.com/content/media/2024/06/notion-rollup-progress-change_thumb.jpg)

This gets the job done, but I wanted to make this column a bit more visual and fun.

To do that, I edited the Progress column property to show the calculated percentage as an orange progress bar instead of a simple number:

![](https://proxy-prod.omnivore-image-cache.app/1498x1010,sMUuR6cR9FK8FhsxkEkQk8Bfor3LIpNbFls9EedeVrs0/https://hulry.com/content/images/2024/06/notion-show-percentage-progress-bar.png)

This created a beautiful progress bar that updates as I check off tasks from the project:

0:00

 /0:03 

![](https://proxy-prod.omnivore-image-cache.app/0x0,s1Kqkv774xEbsPlKDc7Yye7-2ac5hByfja92NWjhvcxU/https://hulry.com/content/media/2024/06/notion-rollup-progress-bar-change_thumb.jpg)

Now, while the Tasks column in the Projects database is a nice indicator of all tasks added to a project, the database view quickly gets messy as more and more tasks are added to each project.

Also, I didn't need to see the tasks here, since opening a project page already shows all the linked tasks.

To make the Projects database look cleaner and compact, I hid the Tasks column from the database view through the database options menu:

0:00

 /0:09 

![](https://proxy-prod.omnivore-image-cache.app/0x0,s_BPFlqb5l3NM0X1SuRLxuRo0kOMe8GRmujIwOhMWeEA/https://hulry.com/content/media/2024/06/notion-hide-tasks-column-projects_thumb.jpg)

While on the subject of making the Projects database look visually appealing, I switched over the Timeline view and chose to show the Progress property on each timeline element:

![](https://proxy-prod.omnivore-image-cache.app/2000x697,sIvzXo4j3HVddrL0MdYLMihJSJkA6I6YhnZdhpqYNRvc/https://hulry.com/content/images/2024/06/notion-timeline-show-progress.png)

I now had a well-oiled, functional project tracker ready to be used for planning live projects.

But, it was still missing the last piece of the puzzle — milestones.

Milestones help tackle long projects more easily by grouping related tasks into meaningful phases.

Here's how I:

## Added milestones to each project

Milestones could be considered as mini-projects grouping a subset of tasks from a project.

Therefore, each milestone needs to be a separate row on a database, linked to a project and many tasks.

To do this, I created a new database called **Milestones** with two Relation properties linking each milestone to a project and many tasks:

![](https://proxy-prod.omnivore-image-cache.app/1590x660,siJ0VtZIXbwmaXZCHeOFagcX1WknmPyGUy_oWqfR_Lf8/https://hulry.com/content/images/2024/06/notion-blank-milestones-database.png)

Similar to the Projects → Tasks relation, I chose to show the milestones relation on both the Projects and the Tasks database so that I could use this relation on those databases:

![](https://proxy-prod.omnivore-image-cache.app/1430x692,s5sCdGlwIM1RhtuhMcyaLeeDalbppPOzc8DZxpM76gXs/https://hulry.com/content/images/2024/06/notion-show-milestones-on-tasks.png)

With the basic setup done, I created a few milestones and linked them to a project and some tasks:

![](https://proxy-prod.omnivore-image-cache.app/1570x698,spN2OQ4sf7yajzDLLtOlclkrmZK6qDiBYzLaMbdoOskc/https://hulry.com/content/images/2024/06/notion-milestones-linked-tasks-projects.png)

Now, although I had an overall project progress setup, I wanted to go granular and see the progress of each milestone as I finished tasks in it.

Using the same process as before, I added a Rollup property to the Milestones database and configured it to show the percentage of checked tasks in a progress bar style:

![](https://proxy-prod.omnivore-image-cache.app/1570x834,sm0oqe2b433RaCET8fhCMXhjlBndV7nws3u0UdbKuv-8/https://hulry.com/content/images/2024/06/notion-milestones-progress-bar.png)

The beauty of this setup is that now, each project progress reflects the progress of the entire project, across milestones, whereas each milestone reflects granular phase-wise progress:

![](https://proxy-prod.omnivore-image-cache.app/1770x1222,sSlKszSggv4HBcQ_anEnczSZHVv0r6U1GRu6Roz2d0x8/https://hulry.com/content/images/2024/06/notion-projects-milestones-progress.png)

The project is only done when all tasks across all milestones are finished.

With this last workflow setup, I had a fully functioning project tracker built using Notion where I could plan and monitor each of my projects, neatly divided into tasks and milestones.

But before calling it a wrap, I wanted to add one more tiny visual indicator — the milestone in progress beside each project:

![](https://proxy-prod.omnivore-image-cache.app/1560x364,sbaI_qtufG9y3vO8Ov6mhkb6IYxtRTpSwVHoeCIqiBfw/https://hulry.com/content/images/2024/06/notion-active-milestone-example.png)

This wasn't a massively helpful feature, but it was a good quality-of-life improvement that would help me understand which phase of a project I'm currently working on.

To do this I added a:

## Formula to show the active milestone

In the Projects database, I added a new property of type **Formula**:

![](https://proxy-prod.omnivore-image-cache.app/1310x504,sHoqK6Lh9JnxcfhfQ3FjoVNv8T4YMpWKFDXSaeD6-6bY/https://hulry.com/content/images/2024/06/notion-new-formula-property.png)

Then, edited the property to run this formula:

prop("Milestones").filter(current.prop("Progress") < 1).first() 

![](https://proxy-prod.omnivore-image-cache.app/1686x668,sGK2Z0g8T0XvtvKp1rH-kFwFL6MiONwIzjzeq2dyrgkg/https://hulry.com/content/images/2024/06/notion-milestones-formula.png)

This is how the formula works:

We get a list of all the Milestones of a project through the prop("Milestones") function. Then, we filter the list to only include milestones which are not completed, using the milestone's Progress property.

Notion calculates the percentage value of checked tasks in the range of 0–1, hence, we can filter completed milestones if their progress percentage value is 1.

Once we have a trimmed list of all pending Milestones, we limit the list to show only the first item on the list.

If you've sorted your milestones according to order in the Milestones database, this formula will always show the next unfinished milestone:

![](https://proxy-prod.omnivore-image-cache.app/1358x670,siAd3hK5UBW1_TflNynX0H9WVqmv2Uxj35CRDxN4b0Bo/https://hulry.com/content/images/2024/06/notion-sorted-next-milestone-active.png)

With this final detail implemented, the project tracker was ready.

I've been using this tracker to plan and monitor my projects, and I've never once thought of using a separate app.

It's minimal, fast, available on my laptop and phone and gets the jobs done.

Most importantly, I can customise the layout, add new features and make customisations that are otherwise restricted on other apps such as Linear or Jira.

Now, it's time for you to:

## Make this project tracker work for you

While the tracker we built in this guide might be all you need to monitor your projects, feel free to tinker around to make it more suitable for your workflow.

This is the beauty of a tool like Notion. You get a huge range of customisation options to build your optimal workflow.

A small starting step could be changing the icons in your database properties to something meaningful to you.

You can do this by clicking on a property name and choosing a new icon for the property like this:

![](https://proxy-prod.omnivore-image-cache.app/1230x534,sjpzRp7mXx_I12RKamVw-VlsSXGE_qkpHpveYl38ANps/https://hulry.com/content/images/2024/06/notion-customise-property-icon.png)

To serve as a ready-to-use project tracker, or a quick starter to building your custom project tracker, I've enhanced and polished this entire tracker into a Notion template that you can [buy for $2.99 and get started right away](https://store.hulry.com/l/jbugj?ref=hulry.com).

You save the time and effort needed to get the tracker set up for a small one-time fee.

Nevertheless, I hope this guide has helped you build a minimal project tracker and also be familiar with some of the advanced features available in Notion.

Try using this tracker for your next projects.

 Share this article on /[ ](https://twitter.com/intent/tweet?via=thehulry&text=How%20I%20Built%20a%20Minimal%20Jira%20Alternative%20in%20Notion&url=https://hulry.com/notion-project-tracker/) [ ](https://pinterest.com/pin/create/button/?url=https://hulry.com/notion-project-tracker/&description=How%20I%20Built%20a%20Minimal%20Jira%20Alternative%20in%20Notion) [ ](https://www.facebook.com/sharer/sharer.php?u=https://hulry.com/notion-project-tracker/) [ ](https://www.linkedin.com/shareArticle?mini=true&url=https://hulry.com/notion-project-tracker/&title=How%20I%20Built%20a%20Minimal%20Jira%20Alternative%20in%20Notion) 

Subscribe for more like this →

![The Hulry Newsletter](https://proxy-prod.omnivore-image-cache.app/0x0,sidKmOdmbxU_ElVVSkapYZ5rrB9Qy3bmrPsY9968U4nk/https://hulry.com/assets/images/newsletter-stamp.svg?v=0d3e10f942) 

## Be 1% better every week

Join 3,889 others & continue your Workflow journey with more articles like this one and hand-picked:

* Apps
* Books
* Videos
* Keyboard Shortcuts