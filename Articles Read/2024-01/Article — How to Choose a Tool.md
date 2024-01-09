---
id: 43b3d5c4-02ff-4e16-8279-82f3f30d6004
site_name: public voit - Web-page of Karl Voit
author: Karl Voit
date_published: 2021-01-18
date_saved: 2024-01-09
date_read: 2024-01-09
date_archived: 2024-01-09T09:31:40.000Z
original_url: https://karl-voit.at/2021/01/18/tool-choices/
omnivore_url: https://omnivore.app/me/https-karl-voit-at-2021-01-18-tool-choices-18ced49d380
---

 - Site: public voit - Web-page of Karl Voit
 - By: Karl Voit
 - Date published: 2021-01-18
 - Date read: [[2024-01-09]]
 - [Read Original](https://karl-voit.at/2021/01/18/tool-choices/)
 - [Read on Omnivore](https://omnivore.app/me/https-karl-voit-at-2021-01-18-tool-choices-18ced49d380)
 - Tags:  #Technology  #Software 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
* Updates  
   * 2021-08-09 Emphasizing "non-requirements" for analysis as well as tool choice steps.  
   * 2023-06-12 Further arguments for raising awareness on issues of privacy, data-protection and lock-in situations.

One single tool can not be a perfect fit for all sets of requirements. You need to differ between different situations, frequency of use, preconditions related to the user's knowledge, user interface requirements, and so forth.

On the other hand, for each given tool, there exists at least one set of requirements where this particular tool is a perfect fit. This way, each tool is a legitimate choice for at least one situation.

Since the requirements are defined by our situation alone, the only free variable here is the tool of choice. Therefore, we need to find a match between our current set of requrements at hand and a tool.

Unfortunately, I have to watch people making sub-optimal choices for their software tools too often. Most of the time, the root cause for a bad tool choice is that there was no deliberate process on how to select the tool. [Maslow](https://en.wikipedia.org/wiki/Abraham%5FMaslow) [once said](https://en.wikipedia.org/wiki/Law%5Fof%5Fthe%5Finstrument):

> I suppose it is tempting, if the only tool you have is a hammer, to treat everything as if it were a nail.

For me, the proper way of choosing a tool is following this pattern:

1. Requirements analysis.
2. Choosing a method.
3. Analyze the tools.
4. Choose a tool.
5. Optimization.

In that order.

Let's take a look at each step.

## Requirements Analysis of Your Situation

Sit down and do a [brainstorming session](https://en.wikipedia.org/wiki/Brainstorming) on the things you want to accomplish. As high level as possible. You may then break them down to generalized finer grained requirements if necessary. Then summarize your findings and prioritize.

Furthermore, please do add your preferences related to vendor lock-in which is also mentioned in a section below.

From my point of view - and unfortunately ignored by most people - I would also recommend to add your risk appetite related to data-protection in general ([security](https://karl-voit.at/tags/security), [surveillance](https://karl-voit.at/tags/surveillance)) and [privacy](https://karl-voit.at/tags/privacy)\-respecting [handling of your data](https://karl-voit.at/cloud-data-conditions). Most people do not have enough background knowledge and awareness about [the dangers of the cloud](https://karl-voit.at/cloud). You should invest some time learning about actual risk factors here before you wish you'd never gave away your personal data. You can't make anything undone here and you will never actually realize most negative effects that are caused by wrongly interpreted data which gets bought by insurance companies, banks and so forth for standard processes.

In the easiest form, you just categorize everything in:

1. "must haves"
2. "nice to haves" and
3. "non-requirements".

Another approach is to come up with an ordered list.

Expert points for an elaborated spreadsheet with weighted numbers associated to each requirement. For most tool decisions, this is overkill though. Keep it simple. ;-)

I'd also suggest that you archive the result of this requirement analysis. It's very helpful identifying changes in your situation later-on or when you are in a similar situation.

## Choosing a Method

Note that you must not search for a tool or a feature [if you are actually looking for a method](https://karl-voit.at/2021/01/18/feature-vs-method). Sometimes, there are no methods to search for but for example for email management, todo list management, time management and so forth, you have to look for a method before you're looking for any implementation that matches this method.

Search on the web, ask peers, read books. Match the (known) methods to your requirements. By doing so, you learn from the pros. Notice, that you are still independent of any specific technological solution.

## Analyze the Tools Available to You

Search on the web, ask peers, read books.

Locate the most popular tools for a discipline but don't forget to look at small solutions. I would urge you to emphasize on open and flexible tools that may serve you for a long time, if this is of any relevance to you.

Please take a careful look on potential lock-in effects. Most probably, you might need to migrate to a different system in future. Test drive data export, data re-use and data completeness of the exported data. If losing all of your data stored and processed within that tool is no issue to you, you may skip this step.

I've read about too many stories about sad cases where people started to use, e.g., photo managing apps/services like iPhoto or Picasa and ended up with losing many years of photographs or their modifications (cutting, meta-data, ...). You can read about that aspect on [my article about file management](https://karl-voit.at/managing-digital-photographs), section "iPhoto, Picasa, ... Considered Harmful".

This can only be avoided by carefully making your tool choice before actually investing data and time.

Match the found tools to the method of choice.

This should now be much easier after mapping your requirements to the tools. You need to take a closer look at your must have requirements. They all should be fulfilled. Then you can map the nice-to-have requirements as a bonus. The non-requirements help you to acknowledge existing features of a tool you don't really need at the moment.

Only if you do have really good reason, you should modify your requirement analysis results with features you did not think of when coming up with that list in the first place. Avoid the temptation of adding tool features just because they look smart for certain requirements you did not have on your list.

The outcome of this process so far is a tool which suits your original requirements as best as possible.

## Periodical Improvements and Re-Evaluation of Your Requirements and Choices

Constantly optimize your situation. Your world is changing all the time. So are your requirements. If your tool choice was a wise one, most necessary changes should be solved by configuration. Tinkering with the configuration and settings of your tool is easier than switching your tool (again). The more you emphasize on long-term aspects, the more you should add "flexibility" to your requirements in the first step.

You should re-check for a potential lock-in effect when the tool changes over time. It would not be the first incident where a flexible tool loses great export features on the way.

Automatize. If you're doing the same thing all the time, try to find a way of automatize this workflow. Good tools should enable you to delegate stupid, error-prone and time-consuming workflows to the computer.

Re-evaluate your choice for the tool and even the method. When the tool of your choice can not adapt to your changed reality any more, you may need to re-evaluate your choices again. This can go back in this process up to a fresh requirement analysis.

## Disclaimer

The focus of this method is on tools you are planning to use over a certain period of time.

If you need a tool for a short-term project where data export, access and other long-term aspects are not relevant at all: use whatever you feel like. It does not matter. However, the process above also works for those choices.

## Other Approaches

There are other approaches on methods on how to choose a software tool. I'll collect some of them here:

* [Choosing Software · Gwern.net](https://www.gwern.net/Choosing-Software)  
   * It should be maintained.  
   * It should be extensible.  
   * You should be able to understand it.  
   * Try to use standard stuff.  
   * efficiency of a program.  
   * Short configurations  
   * Take one, leave one