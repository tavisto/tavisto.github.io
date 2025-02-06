+++
date = '2025-02-05'
draft = true
title = 'Getting Set Up for Productivity'
categories = ["config", "productivity"]
tags = ["asdf", "homebrew", "nix"]
series = ["Productivity"]
+++

# My First Post

This is my reintroduction to posting anything in a really long time. I'm excited to share my thoughts, configs and other productivity setups that have made my life more organized.

The main tools I want to talk about are:
- Tool Management with Homebrew, Nix, and asdf
- Shell tools and configurations with Zsh and Starship
- Text editing with Vim or Neovim
- Language servers for code completion and linting
- Obsidian, task management and knowledge storage

With lots of topics to cover, I would like to start with how to get set up and keep your tools up to date.

## Tool Managers

Lets start with some of the basic things I've been using to manage the tools I use. There are lots of ways to do this, and I have tried most of them. I don't think there is one correct way, as long as you are able to manage your tools, keep them up to date and remember how it works when it matters. I like to think about this like my mechanic and carpentry tools. I keep the tools needed for the job at hand sharp, in good working order and organized in my tool box. Anyone who has seen my garage can stop laughing now. I try and do the same for the tools I use in my daily work, however it's a lot easier to keep my digital tools organized.

### [Homebrew](https://brew.sh/)

Lets talk about Homebrew for a minute. For lots of tools I really appreciate the simplicity of it. If there is a Homebrew package I generally will use that first. When it all breaks down for me is when you need to pin the version of a tool. It is possible in Homebrew, but you have to fight with `brew` to get it done and it's not always easy to remember how to do it. That version is also global to your system and doesn't let you manage different versions for different projects or needs. This can be good if you need to pin a tool globally, but I have found it to have issues when you are working on an upgrade to a tool such as Terraform and need to have many versions installed as you work your way through all the breaking changes.

One of the great features added recently is the ability to use a `Brewfile`. This is like a lock file of all the tools you are using. It's great for setting up a new machine and not being afraid of a catastrophic failure. This very clearly takes a lot of it's syntax from Ruby's Bundler and works in a similar way. You can dump the `Brewfile` and then keep that file in source control.

{{< notice tip>}}
```bash
brew bundle dump
```
This will create a Brewfile in the current directory with all the tools you have installed with Homebrew including all the casks and taps.

Here is a snippit of my `Brewfile`
```text
tap "homebrew/cask-fonts"
brew "asdf"
brew "atuin"
brew "neovim"
brew "starship"
cask "font-fira-code-nerd-font"
cask "font-hack-nerd-font"
cask "obsidian"
```
{{< /notice >}}

### [NIX](https://nixos.org/)

Nix is a great tool for managing tools, however it's the other end of the extreme from Homebrew. It allows you to have a reproducible environment for your projects. However it does this at the expense of a much more complicated setup. The learning curve is very steep and it's not always easy to remember how to do things. There is documentation, but you kind of need to immerse yourself in the ecosystem for quite a while for any of it to make sense. I have not been able to dive into it enough to have more opinions so far but it's on my list of things to learn more about.

### [asdf](https://asdf-vm.com/)

Somewhere in the middle is asdf. It's a great tool for managing versions of tools. It's not as simple as Homebrew, but it's not as complicated as Nix. It's a great middle ground for managing tools. It's easy to remember how to use and it's easy to manage different versions of tools for different projects. It's also easy to pin versions of tools for a project. The plugins are plentiful and all work the same way. I avoided it for a long time because I already had tools for each language or tool that would manage those specific tools. However after adding the third or forth tool that was modeled on rbenv I decided to give it a try.  I recently had a chance to set up a new machine and made it the primary way to install and pin tooling. I haven't converted everything to use it yet because some things I don't mind Homebrew always keeping at the latest version.

asdf uses a `.tool-versions` file in the root of your project to pin the version of the tool you want to use. This is great for projects that need a specific version of a tool. It is also great for setting up a new machine and getting all the languages and versions installed. If you are not in a specific project this file is kept in your `$HOME` directory.

Unlike Homebrew that just installs the tools into a path and has you add that to your PATH variable, asdf installs the tools into a whole bunch of directories kept in your `$HOME` directory. It is able to manage all the different versions by maintaining little shims in your `$PATH` that point to the correct tools. I like this approach because it's a lot more automatic but you can still see what is going on if you care to dig.

{{< notice tip>}}
Before you can use asdf you need to install the plugins. Here are the main ones I use:
```bash
asdf plugin add python
asdf plugin add ruby
asdf plugin add nodejs
asdf plugin add opentofu
asdf plugin add tflint
```

Then you can install the versions you need. Here is the `.tool-versions` file I use.
```text
python 3.13.1t
ruby 3.3.6
nodejs 23.4.0
opentofu 1.8.8
tflint 0.55.0
```
{{< /notice >}}

I hope someone finds this useful, even if that person is just me in several years when I need to remember how I did this.

 -- Tavis
