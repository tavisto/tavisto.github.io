---
layout: post
title: ! 'New Media: The quest begins'
tags:
- FreeNas
- Home Theater
- Multimedia
- OS X
status: publish
type: post
published: true
icon: picture 
---

The first thing I have done  on my quest to free myself from cable television providers is set up a media server. I have done this in two parts, storage and media management.

## Storage

In order to easily stream media to all my devices I decided I needed a robust storage system. After doing some research and asking some knowledgable people for some recommendations I have decided on a        solution.  I have built a NAS ([Network Attached Storage](http://en.wikipedia.org/wiki/Network_attached_storage "http://en.wikipedia.org/wiki/Network_attached_storage")) for  all my data needs. I was mostly able to use parts I had already, so my cost was quite low. However I did buy a new enclosure for hard drives for expansion possibilites. It's just a glorified SATA controller, but expands my capacity quite a bit. [This](http://www.newegg.com/Product/Product.aspx?Item=N82E16816111177) is it if anyone is interested, I got a much better deal though.  For    starters I installed [FreeNAS](http://www.freenas.org/), a port of FreeBSD that has all the utilities built in for managing any size of storage array. I found this very easy to set up and get working. All I really had to do was install my drives into the machine and install the OS onto a usb thumb drive, to keep the hard drive ports open. A few configuration settings in the web         based management interface and "BAM!", instant storage.  I was able to set up a partition that included my two 1.5T drives in a mirrored configuration using [ZFS](http://en.wikipedia.org/wiki/Zfs). What this really means is that if one of my drives fail, everything is still available on the other one. I may want to make a more robust setup in the future, but that will depend on what size and type of drives I get. For the time being 1.5TB of redundant space should be enough to get started.

Getting this to work with my OS X machine was really easy. I simply set up a shared [AFP](http://en.wikipedia.org/wiki/Apple_Filing_Protocol) directory on my file server, browsed   to it on my OS X machine and was ready to fill it with content.

## Content

The first order of business was to organize the collection of media files I have collected over the years into a single location. After that, the question becomes how to access it all. As with a storage      solution I asked around to see what other people are using. What I found is a large array of services, tools, and media managers. In order to chose one I had to narrow down my criteria. This is the list I    came up with:

*   Works with my PS3
*   Works with my iPad
*   Works with any OS X machine
*   Able to stream content from my library
*   Able to aggregate content from the rest of the interent
*   Netflix
*   Hulu

I was able to narrow what I wanted down to two different media servers, [Plex](http://www.plexapp.com/) and [MediaLink](http://www.nullriver.com/products/medialink). I have been using MediaLink for quite some time now to stream content from my main library to my PS3. It works  pretty good as a simple media server, but does not work with my  iPad or is easy to stream on my laptop. In order to do any of that I need to use Plex, it does everything else I want in a media application.  I was able to find many of the shows I thought I would be        missing through plugins. For example NCIS is available through CBS's website and there is a plugin lets me stream that to any of my devices. I have also found a wide array of internet content such as a [VIM](http://www.vim.org/) screencast that I had no idea existed.

I did compare this to things like [XBMC](http://xbmc.org/) and [Boxee](http://www.boxee.tv/) but there was always some feature or usability thing I       didn't like about either on of those. Plex has a really nice iPad app that not only lets me stream content, but use my iPad as a remote for any other computer streaming content with Plex.  The integration    with Hulu and Netflix is quite good, and requires nothing more than your account information for the respective accounts. I do want to note though, that the Netflix interface is still not as nice as any of   the official Netflix apps, such as the PS3 or the iPad apps.

I have been trying it out with my old Macbook hooked up to my TV in the bedroom. It does quite well but I think that building a replacement is going to be a future post.

In a more irritating turn of events, my main TV has starting acting up and I will need to get it repaired. Hopefully it is nothing major and just needs a new lamp or some other small thing.

I think the coolest part of this whole adventure is some of the integrations I will be able to do. Controlling my media through my iPad and subscribing to shows I want to watch is exactly what I have been    wanting for a long time. DVR and the like have not really helped with this since you have to know quite a bit ahead of time to make it work properly. Searching for a show and being able to watch it is        starting to be like the future of TV that has been promised for quite some time now. I say the future is here, and the only way to make it better is for people like me to try things like this and share       my experiences.
