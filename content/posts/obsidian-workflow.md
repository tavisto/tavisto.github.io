+++
date = "2025-03-30T13:49:24-06:00"
title = "Obsidian Workflow"
description = "Putting it all together"
slug = "obisidian-workflow"
authors = ["Tavis Aitken"]
tags = ["obsidian"]
categories = ["productivity"]
series = ["Obsidian"]
summary = "Now that we have all the parts, lets build a workflow that will help us keep organized and on task. Using some of the features we set up in the previous posts, we can create a workflow that will help us get things done."
+++

# Putting it all together

Now that we have all the parts, lets build a workflow that will help us keep organized and on task. Using some of the features we set up in the previous posts, we can create a workflow that will help us get things done.

## Daily Notes

I find it really helpful to start my day by creating a new daily note. I don't want this to be too automatic, as I find the act of clicking the button to create the note acts as a mental queue that I am starting my work day. This will use the template I have set up in the Periodic Notes plugin using the setup I explained [previously](/posts/obsidian-plugins/#periodic-notes)


### Daily Note Layout

Let's have a look at how I have structured my daily note.
The template has four sections:
- `## Next`: New Tasks to work on today.
- `## Things that happened today`: Interesting events of the day.
- `## Notes`: Meeting notes and other conversations.
- `## Tasks`: Dataview sections for task queries
  - `### Due Today`: Tasks that are due today.
  - `### Done Yesterday`: Tasks that were completed yesterday.
  - `### Everything Else`: All other tasks that are not done and not tagged with #janitor.

Here is the entire template:
```markdown
---
date: {{date:YYYY-MM-DD }}
tags:
  - daily
---
# {{date:dddd MMMM Do YYYY }}

## Next
- [ ] Cancel any leftover tasks that don't need to be done anymore #janitor

## Things that Happened Today
-
## Notes

## Tasks
### Due Today
```tasks
not done
group by tags
due on or before today
show tree
    ```

### Done Yesterday
```tasks
done yesterday
    ```

### Everything Else
```tasks
not done
group by tags
filter by function task.file.folder.includes('Periodic')
tags do not include #janitor
status.name includes todo
show tree
    ```
```

### First thing of the day

The first todo list item every day is to review any open tasks. This is where I go review tasks that may have piled up and make sure they are still needed. This task is tagged with the `#janitor` tag, so that I can filter it out from any other queries. Without this filter, these tasks would show up where it would clutter up the list.

The next thing I do is to write down what I intend to do that day. I usually go look at my calendar and make a task for each meeting I have. If it is a meeting with someone 1-1 I will link it to the corresponding note so it's easy to open. I try not to duplicate any tasks that carried over from previous days, but if I do I will rewrite them to be in the context of the current day and complete out the old one.

## 1-1 Meeting Notes

I keep a special note for my 1-1 meetings with people. It is just a running note per person, with headers for each date we meet. I then add any topics that we cover during the meeting. Typically I will add a task ahead of time for things I want to make sure to cover. Any tasks that come out of the meeting get added to the daily note so they don't get lost.

Here is the template snippit for the 1-1 meeting notes:
```markdown

# {{date:dddd MMMM Do YYYY }}

## Topic Covered
- Item
```

## People

Keeping track of the people you interact with is important. I know I can't remember everything about everyone, so I try to keep a note for each person I work with. This is a simple note with their name as the title and a few sections. I put what their official job title is, where they are located including what time zone they are in, and general section for any other things I want to remember about them. This is also a great place to put any great quotes I hear them say.

```markdown
# [Name](link to wiki or other internal place like an org chart etc.)
## Title

### Location

### General
```

## Conclusion

This is the workflow that I have been using for a few months now. I didn't want to to overcomplicate it, but I also wanted to make sure I had the tools I needed to stay organized. There are quite a few improvements I would like to make, but keeping things simple and maintaining the habit of using them has been key to making this work for me.

-- Tavis
