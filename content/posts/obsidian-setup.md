+++
date = "2025-02-10T07:00:00-08:00"
title = "Obsidian Setup"
description = "A brief overview of how to set up Obsidian and sync your notes"
slug = "obsidian-setup"
authors = ["Tavis Aitken"]
tags = ["obsidian", "syncing", "cloud-storage"]
categories = ["productivity"]
series = ["Obsidian"]
+++

# What is Obsidian?

[Obsidian](https://obsidian.md) is a general purpose note-taking tool with a neat trick. Its clever design uses the fact that everything is simply markdown configured and manipulated using plugins. It has become very popular with the [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten) method of note taking and knowledge management. The main idea being that you write down all your ideas in a simple way that you can search and reference later. It has some really great built-in features that make it very useful even right out of the box with the default configurations. Things can be made as complex or as simple as you care to make them depending on your needs and desires.

## Vaults and Syncing

The top level organization in Obsidian is called a vault. This is where all your notes and other files are stored. It's a directory on your file system that contains all the markdown files that you create and edit in Obsidian. You can have multiple vaults and switch between them easily. This is especially useful for keeping work and personal notes separate or for having a vault for a specific project.

One of the major benefits of a vault being just a folder of files is that you can use almost any tool that is built to help manage any other type of file. Let's dive into a few of them.

### Local
The simplest thing you can do is just start a vault in a local folder. It's not shared anywhere and is only available on the machine you created it on. However the best part of the way the vaults are stored is that you can move them around and copy them to new places and everything still works the same. This is a great place to start until you figure out how you want to set up your syncing.

I tend to create a top level folder in my home directory where all my vaults live even if they don't sync anywhere. This makes it easy to find them, although when using some of the other methods you generally have to move them to that service's folder.

```shell
lt ~/Obsidian
├── Obsidian
│   ├── git-test
│   ├── notes
│   ├── personal
│   └── todo-testing
```

### Git


For those non technology folks, [Git](https://git-scm.com/) is primarily a source control tool. It was developed to manage the development of the Linux kernel code and is now the dominant way to manage software development. This means there are lots of tooling around it and very large platforms for managing repositories such as [Github](https://github.com) and [Gitlab](https://gitlab.com).

This could be a good choice if you want to keep change history and sync your notes using a private repository on your git platform of choice. It does have some drawbacks when it comes to the workflow and usability across platforms though. Specifically mobile clients do not handle this method of syncing very well. There is a plugin to help manage this called [Obsidian Git](https://github.com/Vinzent03/obsidian-git) that does some of the work for you, but still has some limitations.

### Cloud Drives

Once again the fact that a vault is just a folder full of simple files means that any of the file storage services can work very well for syncing your vaults. This can be especially useful if your employer provides a cloud storage account of some sort and you want to keep a vault on official sanctioned methods. I used to keep my work notes all in a vault on my Google Drive connected to my work account. This worked fine, but didn't allow any access on mobile devices.

### Obsidian Sync

The fine folks who make Obsidian for a living also have a paid service that can manage your vaults for you called [Sync](https://obsidian.md/sync). I moved to this service after having some issues with Dropbox, iCloud and Google Drive syncing. It is a paid service, but is fairly reasonable for the features it provides. It's also built right into the Obsidian app so you don't have to worry about setting up any other tools to manage your syncing. I am a believer in paying for software that I use and as much as I use it to manage my task management and note taking I think it's worth it.

{{< notice tip >}}
A quick note about iCloud and using Obsidian on [iPhones and iPads](https://help.obsidian.md/getting-started/sync-your-notes-across-devices#iPhone+and+iPad+syncing). The Obsidian app for iOS lets you load your vaults, but only from iCloud or Obsidian sync. You can use iCloud to sync your vaults between devices, as long as all those devices are on the same Apple account. I have seen some issues with file syncing being very slow or acting strangely with iCloud and highly recommend using Obsidian Sync if you are going to use Obsidian on iOS.
{{< /notice >}}

## So much more

Now we know how to write stuff down and make sure we save it somewhere. However there is a lot more to configure to get the ultimate digital brain dump set up. In the next few posts I am going to be covering which plugins, themes and other tricks I use to try and stay on target in my day to day work.

 -- Tavis
