---
title: Why did I start this blog
author: ErwinTATP
date: '2020-08-09'
slug: why-did-I-start-this-blog
description: Because I hate OriginLab.
---
It all started with OriginLab. Or rather, the hatred towards it.

As a chemistry graduate student with limited programming experience, I had to plot and summarize huge amount of data coming from various scanners - IR, UV-Vis, Current-Voltage, NMR, you name it. And, as a chemistry graduate student trained in China, I picked up pirated versions of OriginLab as my primary tool.

Because "everyone else had been using it", they said. "It is powerful and does things Excel cannot do", they said. Whenever I meet a new testing device and ask about how the data are processed for my reports, all the colleagues and engineers would answer, "save them as [insert format here] and do it in Origin". 

As if it is granted for everyone. Well, it isn't.

Origin needs a license to activate. For many academic softwares, "not activated" means "you can still view files but not write it" or "you cannot do anything but there's free alternatives that can do this for the file." There are free readers for pdf, well-known media processor ffmpeg and imagemagick, free Office suite from LibreOffice, not to mention the mighty and handy Google docs. But for Origin, it is "I've made your data into formats only I can access and you're not seeing any unless you've paid me".

To get that license, you'll need an .edu mailbox, and handling out every personal data that the  corporation is definitely not giving out to anyone. Then you'll get the access to this "enhanced" version of Excel for a whopping 6 months. You'll have to repeat the process again and again, until one day you left the institute and all the fruits from these sleepless nights falls into oblivion. Oh you say pirated copies? Well, OriginLab updated their licensing technologies and the none of the older copies works for now; and there's the copyright issues during the publishing processes - journals with IF higher than 1 would very likely to reject anything plotted with pirated stuff.

Aaannnnnd here's this whole "enhanced Excel" claims. From my limited interacts with these researchers, their Excel techniques are nowhere near their academic accomplishments. In fact, I bet most Excel users have no idea how to use spreadsheet softwares properly - that's why there are these online Excel classes costing hundreds of bucks. 

For my master research, I need to plot [current-voltage data](https://t.ly/q47H) of transistors measured by an aged scanner. In each scan, the voltage is increased from zero to a certain value ("forward scan"), then drop back to zero ("backward scan"). The data for both scans are combined together in a datasheet, with a few hundred rows of codes about equipment set-up, which I later found out that are just garbage that has nothing to do with the actual equipment parameters. I have to extract the actual scanning from the code mess, separate the forward and backward scans, and create at least 3 plots for each scan - current, derivation of current, and square-root of the current. Furthermore, to accurately reflect device performance, for every point on that square-root plot, I have to calculate the slope from the linear fit for the 4 data points after it and find out the largest.

Oh, and for each experiment I need to scan 30+ transistors.

For every single one of them, I have to identify the correct region to select, and copy-paste data from the raw datasheet. Most people can calculate the differentials and square roots fairly easily with basic functions; however, for the "5-point-fittings" they have to actually plot it, move the plotting sections until the slope *seems* largest, read the data from the chart, and manually type the data on chart into the final recordings. It was very common for people to spent an entire day on processing these data.

Then I created something using some index functions, dynamic ranges, and loads of inefficient if-else codes. The final product is a spreadsheet that processes everything with a single copy-paste. You feed it raw data and it automatically filters the actual data, separate the scanning, and extract the fitting slopes without plotting (the code for which is surprisingly complex). I still need one or two hours to calculate all 30 devices, but it was way better than before.

But I cannot recreate that in Origin. It doesn't have all the indexing, filtering and calculation functions for automatic processing. In fact, if you simply copy paste some data, it even have hard times to tell the single header row from the rest of data. I have to pre-process spreadsheet data in another spreadsheet before using them in Origin. 

After all the additional wrangling, you would probable expect the output "enhanced plot" from the Origin. Well, the plots looks exactly identical to the excel ones, sometimes even more horrible. But adjusting the appearance is much, much more infuriating. Panel borders, axis, ticks, labels, curves and points - each have a complex dialog box mixing the critical parameters with pointless options. And for the next graph you'll have to repeat the process again. Though they do have a "copy every style element" function, it never worked as I intended.

There you have it. An "enhanced Excel" without easy-to-access automatic data processing functions, creates plots that are not any better in quality but much harder to adjust, and creates files only readable by itself. They even [edited their own Wikipedia page](https://en.wikipedia.org/w/index.php?title=Origin_(data_analysis_software)&action=history) to promote themselves; even more pathetic, the Wikipedia community labeled it as "may have been created or edited in return for undisclosed payments" and nobody has contents sufficient enough to fix it.

{{< figure src="/post/2020-08-09-why-did-i-try-to-start-a-blog_files/Undisclosed_payments.png" alt="Wikipedia heading template of the Origin article, implying the content may have been edited in return of payments." position="center" style="border-radius: 4px;" caption="You don't see this every day." >}}

And the Chinese academia buys it all. Well, "buying" is probably inaccurate as most of them didn't actually pay for the software.

The college I'm currently in also haven't purchased the software. Unlike the aforementioned institutes and their no-speak-no-tell attitude towards pirated softwares, my college strictly disallowed us using it for publications since they didn't pay for it. Hooray!

Yet my colleagues still need to create those scanning plots and fittings, and they did it manually. So naturally, I introduced my ultimate spreadsheet to them - and they complained that hours of copy-paste is still somewhat frustrating. Well then, I have to develop something even more simple. 

Then I remembered a long time friend of mine that complained time after time about this "R programming" during her master study. I looked it up back then, but didn't think too much about it. When COVID-19 arrived, I was stuck in apartment for 2 weeks, and for a further month I didn't need to prepare the biweekly report to my supervisor. I decided to do some scripting. Fast forward to when my lab went back to full operation, the script I created reproduces everything the old automatic spreadsheet did, except that it processes 50 raw datasheet in around 1 minute with a single click.  

Naturally, for a programming dumbass like me, I did tons of Google-fu during the scripting progress. That's where I stumbled upon the universe of rmarkdown that integrates the r-graphs into books, posters, slides, and websites from the same source file. From then on, I ditched my powerpoint and started using xaringan as my primary presentation tool. After another wave of pandemic swept my city, I'm stuck at home again, and decided to see if I can really create a blog like whatever the language claimed.

A few days later, here I am.