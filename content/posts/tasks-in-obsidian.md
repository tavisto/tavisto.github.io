+++
draft = true
date = '2025-02-08'
title = "Task management in Obsidian"
description = "How I manage tasks using Obsidian"
slug = "tasks-in-obsidian"
categories = ["productivity"]
series = ["Productivity"]
tags = ["obsidian", "task-management"]
+++


# [Obsidian](https://obsidian.md/)
Obsidian is a general purpose not taking tool with a trick up it's sleeve. The trick is that it's simply markdown with infinite configurability using plugins. It has become very popular with the [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten) method of note taking and knowledge management. The main idea being that you write down all your ideas in a simple way that you can search and reference later. It has some really great built in features that make it very useful even right out of the box with the default configurations. Things can be made as complex or as simple as you care to make them depending on your needs and desires.

## Vaults and Syncing
The top level organization in Obsidian is called a vault. This is where all your notes and other files are stored. It's a directory on your filesystem that contains all the markdown files that you create and edit in Obsidian. You can have multiple vaults and switch between them easily. This is especially useful for keeping work and personal notes separate or for having a vault for a specific project.

One of the major benefits of a vault being just a folder of files is you that you can use almost any tool that is built to help manage any other type of file. Lets dive in to a few of them.

### Local
The simplest thing you can do is just start a vault in a local folder. It's not shared anywhere and is only available on the machine you created it on. However the best part of the way the vaults are stored is that you can move them around and copy them to new places and everything still works the same. This is a great place to start until you figure out how you wan to set up your syncing.

### Git

For those non technology folks, [Git](https://git-scm.com/) is primarily a source control tool. It was developed to manage the development of the Linux kernel code and is now the dominant way to manage software development. This means there are lots of tooling around it and very large platforms for managing repositories such as Github and Gitlab.

This could be a good choice if you want to keep change history and sync your notes using a private repository on your git platform of choice. It does have some drawbacks when it comes to the workflow and usability across platforms though. Specifically mobile clients do not handle this method of syncing very well. There is a plugin to help manage this called [Obsidian Git](https://github.com/Vinzent03/obsidian-git) that does some of the work for you, but still has some limitations.

### Cloud Drives

Once again the fact that a vault is just a folder full of simple files means that any of the file storage services can work very well for syncing your vaults. This can be especially useful if your employer provides a cloud storage account of some sort and you want to keep a vault on official sanctioned methods. I used to keep my work notes all in a vault on my Google Drive connected to my work account. This worked fine, but didn't allow any access on mobile devices.

### [Obsidian Sync](https://obsidian.md/sync)
The fine folks who make Obsidian for a living also have a paid service that can manage your vaults for you. I moved to this service after having some issues with Dropbox, iCloud and Google Drive syncing. It is a paid service, but is fairly reasonable for the features it provides. It's also built right into the Obsidian app so you don't have to worry about setting up any other tools to manage your syncing. I am a believer in paying for software that I use and as much as I use it to manage my task management and note taking I think it's worth it.

{{< notice tip>}}
A quick note about iCloud and using Obsidian on [iPhones and iPads](https://help.obsidian.md/getting-started/sync-your-notes-across-devices#iPhone+and+iPad+syncing). The Obsidian app for iOS lets you load your vaults, but only from iCloud or Obsidian sync. You can use iCloud to sync your vaults between devices, as long as all those devices are on the same Apple account. I have seen some issues with file syncing being very slow or acting strangely with iCloud and highly recommend using Obsidian Sync if you are going to use Obsidian on iOS.
{{< /notice >}}


## Plugins

Now that we have a simple vault setup and can read and write notes across devices. Lets figure out how to to do some more advanced things to make this more useful than just a text editor. All the plugins I use are available in the community plugins section of the Obsidian app. There is a handy search feature that can help you find most types of things you might want to do. I highly recommend starting out simple and only adding plugins when you really understand your needs and how they can be met with a plugin. I have started over more than once because I had a lot of plugins that I wasn't using or were conflicting with each other.

### Periodic Notes

### [Dataview](https://blacksmithgu.github.io/obsidian-dataview/)

Dataview is one of the more powerful ones that lots of other plugins are built on top of. I will let the author describe it in their own words:

> Dataview is a live index and query engine over your personal knowledge base. You can add metadata to your notes and query them with the Dataview Query Language to list, filter, sort or group your data. Dataview keeps your queries always up to date and makes data aggregation a breeze.
> [^1]

The main benefit is that you can add metadata to things in your notes and then query them to get lists of things that match your criteria. The queries can be as simple as a list of notes that have a specific tag or as complex as you can imagine.

The official documentation on how to add metadata and what kinds of things you can do with it is very good. However the main thing you need to know is that you can add metadata to a note by adding a YAML frontmatter block to the top of the note. This is a block of text that is surrounded by `---` and contains key value pairs that you can use to query later.

The big one I use is a `tags` key that I use to add tags to at the very least my daily notes to separate them out when querying later.

```yaml
---
date: 2025-02-08
tags: [daily]
```

You can then query for all notes that have the `daily` tag and get a list of all the notes that you have tagged that way. Sometimes more importantly you can use it as a filter to either only find stuff in your daily notes or to exclude them from a dataset.

A simple query to get all the notes that have the `daily` tag would look like this:

```SQL
```dataview
TABLE file.path FROM #daily
SORT date DESC
```

This would output a nice table like so:

| file(1) | file.path |
| ------- | --------- |
| 2025-02-08 | /path/to/your/vault/2025-02-08-Mon.md |

The great thing about that is that it's a live query. This means that if you add the `tags: [daily]` to the frontmatter of a note it will show up in the list the next time you run the query. This means that if you put a `dataview` query in a note or anywhere in your vault you can show dynamic content that is always up to date without having to do anything. As you can start to imagine this can be very powerful for things like making lists and keeping that list in front of you.

### Tasks

Talk about the tasks plugin

## Themes

[^1]: [Dataview Overview](https://blacksmithgu.github.io/obsidian-dataview/#overview)
