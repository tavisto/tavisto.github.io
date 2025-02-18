+++
date = "2025-02-11T07:00:00-08:00"
title = "Obsidian Plugins"
description = "A few plugins that make Obsidian worth it."
slug = "obsidian-plugins"
authors = ["Tavis Aitken"]
tags = ["obsidian", "plugins", 'task-management']
categories = ["productivity"]
series = ["Obsidian"]
summary = "Now that we have a simple vault setup and can read and write notes across devices, let's figure out how to do some more advanced things to make this more useful than just a shiny text editor. All the plugins I use are available in the community plugins section of the Obsidian app. There is a handy search feature that can help you find most types of things you might want to do. I highly recommend starting out simple and only adding plugins when you really understand your needs and how they can be met with a plugin. I have started over more than once because I had a lot of plugins that I wasn't using or were conflicting with each other."
+++

# Plugins

Now that we have a simple vault setup and can read and write notes across devices, let's figure out how to do some more advanced things to make this more useful than just a shiny text editor. All the plugins I use are available in the community plugins section of the Obsidian app. There is a handy search feature that can help you find most types of things you might want to do. I highly recommend starting out simple and only adding plugins when you really understand your needs and how they can be met with a plugin. I have started over more than once because I had a lot of plugins that I wasn't using or were conflicting with each other.

## Periodic Notes

The first plugin I want to talk about is the [Periodic Notes](https://github.com/liamcain/obsidian-periodic-notes) plugin. There is a built-in plugin for a daily note, but it lacks quite a few of the features that this plugin provides. They both allow you to create notes from a template, and to specify the location. However, the Periodic Notes plugin allows you to get especially clever with the folder structure and templating. I use it to create a daily note in a folder structure that looks like this:

``` plaintext
2025
├── 01
│   ├── 2025-01-01-Wed.md
```

This keeps the daily notes organized and sortable chronologically, while remaining human-readable in any list they may appear.

To set this up simply add the following string in the Format field of the Periodic Notes settings:

``` plaintext
YYYY/MM/YYYY-MM-DD-ddd
```

Under the hood Obsidian is using the [momentjs](https://momentjs.com/docs/#/displaying/format/)library to format the date string. If there is a date format you like, there is a very good chance you can use it here. Remember folks, that when it comes to dates and date math, [never write your own library](https://www.youtube.com/watch?v=-5wpm-gesOY).

The other powerful thing that this plugin supports is the ability to do a Weekly, Monthly, Quarterly or even Yearly notes. The idea being that you could do a retro and look back on what you have done over that time period. However, I haven't effectively used this feature yet. It sounds like a good idea, but does require more discipline than I currently have to make it work.

There is a lot you can do on your daily notes, but we will need some more plugins to handle some of the really interesting tricks.

{{< notice tip >}}
I have found that the daily notes are a great place to start your day. I have the [Calendar](https://github.com/liamcain/obsidian-calendar-plugin) plugin set up so I can click on any day and it will open that note.
{{< /notice >}}

## Dataview

[Dataview](https://blacksmithgu.github.io/obsidian-dataview/) is one of the more powerful tools that lots of other plugins are built on top of. I will let the author describe it in their own words:

> Dataview is a live index and query engine over your personal knowledge base. You can add metadata to your notes and query them with the Dataview Query Language to list, filter, sort or group your data. Dataview keeps your queries always up to date and makes data aggregation a breeze.

The main benefit is that you can add metadata to things in your notes and then query them to get lists of those specific things later. The queries can be as simple as a list of notes that have a specific tag or as complex as you can imagine.

The official documentation on adding metadata and its many applications is excellent. In short, add metadata to a note by including a block at the top with the required information. This is a block of text that is surrounded by `---` and contains key value pairs that you can use to query.

The best example of this that I use is the`tags` key. I use it to add a list of tags in my daily notes to separate them out when querying in other places.

```yaml
---
date: 2025-02-08
tags: [daily]
```

You can then query for all notes that have the `daily` tag and it will return a list of all the notes that you have tagged that way. Importantly, you can use it as a filter find only the stuff in your daily notes or to exclude them from a dataset.

A simple query to get all the notes that have the `daily` tag would look like this:

```SQL
    ```dataview
    TABLE file.path FROM #daily
    SORT date DESC
    ```
```

This would output a nice table like so:

| file(1) | file.path |
| ------- | --------- |
| 2025-02-08 | /path/to/your/vault/2025-02-08-Mon.md |

The great thing is that it's a live query. This means that if you add the `tags: [daily]` to the metadata of another note it will show up in the list. This means that if you put a `dataview` query in any note anywhere in your vault you can show dynamic content that is always up to date without having to do anything. As you can start to imagine this can be very powerful for things like making lists and keeping that list in front of you.

### Tasks

All of those other plugins are only the building blocks to make this one really shine. There are a few plugins in this genre, but none of them really did enough for me to be useful.
The [Tasks](https://publish.obsidian.md/tasks/Introduction) plugin is both very simple and the most complex part of my configuration.

The basic building block of this plugin is the humble markdown checkbox.
```markdown
- [ ] This renders to a checkbox in Obsidian
- [x] This is a checked checkbox
```
Which looks something like this depending on your theme:
- [ ] This renders to a checkbox in Obsidian
- [x] This is a checked checkbox

The plugin adds a few features on top of this to make it more powerful. You can add tags, dates, priorities, and even change what kind of item it is depending on what you put in between the brackets. It does this by leveraging the Dataview plugin as well as its own style of metadata using emojis.

My favorite neat thing to do is maintain a "Quotes" note, that simply has a query for any task that has a `"` as its type.

```markdown
- ["] This is a fun quote from someone or something i heard today.
```

This will show up in the Quotes note as a quote, and tell you what file it came from.
```markdown
    ```tasks
    filter by function task.status.symbol === '"'
    ```
```

This is just one of the many types that can be used here. You can even customize them as long as you have a theme that supports it and knows how to render it.
I have only just started to explore the things I can do with this plugin, and I am sure there is more to come.

## Still needs to look good

With these basic plugins installed you can have a very organized daily routine. The default themes look fine, but to leverage a lot more of the Tasks plugin there are some themes that are built to support it. However, that's a topic for another post.

-- Tavis

