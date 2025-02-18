+++
date = 2025-02-15T07:07:44-07:00
title = "Obsidian Themes"
description = "What to look for in a theme for Obsidian"
slug = "obsidian-themes"
authors = ["Tavis Aitken"]
tags = ["obsidian", "themes"]
categories = ["productivity"]
series = ["Obsidian"]
summary = "First, we set up syncing, then we became productive. Now, let's look at making it all look nice."
+++

# Making this look good

First, we set up syncing, then we became productive. Now, let's look at making it all look nice. Obsidian uses a pretty standard theme system with lots of choices available. The one I have been using is [AnuPpuccin](https://github.com/AnubisNekhet/anuppuccin). It has a good balance of colors, light and dark modes, as well as a very expansive collection of custom task status.

### Customizing the look

The number of settings in these themes is huge, I still have only scratched the surface of what is possible. I decided to use mostly the defaults to get started, but some of the basics are really nice to enable right away.

{{< notice tip >}}
This theme uses the [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) plugin to allow for a lot of customization such as extended themes and custom snippets. A lot of the configuration for the theme is done in the settings for the plugin.
![AnuPpuccin-Extended](anuppuccin-extended.png)
{{< /notice >}}

## Headers And Folders

One thing I really appreciate in a good theme is the ability to have each header size be a different color. This makes them stand out from one another and helps with organization. A lot of the header sizes are not all that different, so having a distinct color change can really help the different sections pop out clearly.

{{< tabgroup >}}
{{< tab name="Screenshot" >}}
![Headers](headers.png)
{{< /tab >}}
{{< tab name="Source" >}}

```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

{{< /tab >}}
{{< /tabgroup >}}

One of the additional [snippets](https://help.obsidian.md/Extending+Obsidian/CSS+snippets) included in the AnuPpuccin theme is the ability to have folders in the sidebar be different colors. If you download the snippet, and add it to your snippets folder, you can then adjust the colors to your liking.



## Code and Syntax highlighting

As someone who spends a lot of time reading code, having good syntax highlighting helps to quickly understand what is going on by applying color to the different parts of the code.
Obsidian has built-in syntax highlighting using a standard library. Check out the language list for [Prism.js](https://prismjs.com/#supported-languages) if you are interested in what it can do. Whatever theme you choose will support it and can set the style. Most file formats and programming languages are supported out of the box so try it out!

These can be used by adding a blockquote with a hint as to what it contains.

{{< tabgroup >}}
{{< tab name="Screenshot" >}}
![PythonCode](python-code.png)
{{< /tab >}}
{{< tab name="Source" >}}

```markdown
    ```python
    def main():
        print("Hello world.")

    if __name__ == "__main__":
        main()
    ```
```
{{< /tab >}}
{{< /tabgroup >}}

Inline code is also supported and should look like this: `print("Hello world.")`, but it does not have the same syntax highlighting as the code block.

## Integration with the tasks plugin

Some themes offer special features that can be used with the tasks plugin. They do this by adding custom icons to the checkboxes.
The default theme doesn't display anything special for custom task status fields. There are however themes that make them look quite a lot better like the one I mentioned earlier.

{{< tabgroup >}}
{{< tab name="Screenshot" >}}
![TaskStatus](task-status.png)
{{< /tab >}}
{{< tab name="Source" >}}
```markdown
## Example Tasks

- [ ]  `space` Unchecked
- [x]  `x` Checked
- [>]  `>` Rescheduled
- [<]  `<` Scheduled
- [!]  `!` Important
- [-]  `-` Cancelled
- [/]  `/` In Progress
- [?]  `?` Question
- [*]  `*` Star
- [n]  `n` Note
- [l]  `l` Location
- [i]  `i` Information
- [I]  `I` Idea
- [S]  `S` Amount
- [p]  `p` Pro
- [c]  `c` Con
- [b]  `b` Bookmark
- ["]  `"` Quote
- [0]  `0` Speech bubble 0
- [1]  `1` Speech bubble 1
- [2]  `2` Speech bubble 2
- [3]  `3` Speech bubble 3
- [4]  `4` Speech bubble 4
- [5]  `5` Speech bubble 5
- [6]  `6` Speech bubble 6
- [7]  `7` Speech bubble 7
- [8]  `8` Speech bubble 8
- [9]  `9` Speech bubble 9
```
{{< /tab >}}
{{< /tabgroup >}}

As you can see, there are lots of types of tasks that you can then turn into other useful tools. I mentioned the "Quote" status in a [previous post](/posts/obsidian-plugins/#tasks) and this is how we can show it off with some style.

## Other themes that work well.

Beyond the AnuPuccin there are quite a lot of other themes out there, but not all have the fancy icons for enhanced checkboxes for use with tasks. Here are some other options that have extended checkbox support:

- [Minimal](https://github.com/kepano/obsidian-minimal)
- [Aura](https://github.com/ashwinjadhav818/obsidian-aura)
- [Things](https://github.com/colineckert/obsidian-things)
- [LYT Mode](https://github.com/nickmilo/LYT-Mode)
- [Border](https://github.com/Akifyss/obsidian-border)

## Make it your own

Find something that works for you and that you enjoy looking at all day. If it's nice to look at and easy to read you will be much more likely to keep it open. I tend to prefer dark themes most of the time, but it is nice to have a light mode for higher contrast sometimes.

 -- Tavis

