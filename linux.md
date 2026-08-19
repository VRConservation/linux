---
title: Linux vs. Windows
subject: Hardware
subtitle: Time to take the plunge!
short_title: Linux
date: 2026-08-18
authors:
  - name: Vance Russell
    affiliations: 
      - 3point.xyz
    email: vance@3point.xyz
license: CC-BY-4.0
keywords: hardware, efficiency, linux, windows, os
abstract: |
  Transitioning from Windows to Linux for daily work use is a worthwhile and often valuable consideration. I describe my personal journey to change motivated by persistent performance frustrations with Windows 11. One laptop and a mini-pc were converted—one running Cosmic Pop!_OS and another running Manjaro KDE Plasma—alongside a headless Debian server. Key benefits include significantly faster application startup times and an overall sense that machines run more efficiently under Linux. Challenges such as Bluetooth connectivity, touchscreen compatibility, and the learning curve of terminal-based workflows are honestly acknowledged, along with practical workarounds. Recommendations for prospective switchers include starting on old hardware, embracing the terminal, using alternatives like OnlyOffice and VS Code, and maintaining a backup Windows machine for software that lacks Linux support. A summary table of pros and cons is provided.
kernelspec:
  name: python3
  display_name: Python 3
exports:
  - format: docx
    template: curvenote
    output: linux.docx
    article_type: Report
  - format: typst
    template: lapreprint-typst
    output: linux.pdf     
---

# Windows OS Frustration
Nearly two years ago, I began to get very frustrated with Windows 11 on a Dell XPS laptop that I used for work. It would get particularly bad when Windows Defender would run in the middle of the mornig, rendering my mouse, some programs, and making everything exceptionally slow for about an hour. I tried everything to reschedule the scans to turning it off, but it just kept running at inopportune moments, like it had a mind of its own.

I had been thinking about switching my main work pc to Linux at the time and one morning when Defender was really bad, I ordered a new PC. I had been experimenting with Linux Mint and Ubuntu on an old laptop that didn't have the memory to install windows 11 and both OS's had brought new life into the machine, running quickly and operating like a pc should: for you!

# Changing to Linux
My Microsoft Surface laptop (I'm aware of the irony) ended up with Cosmic Popos, which is a great operating system built by the folks at System76. It has nice shortcuts, runs well, has cool features like auto tiling. QGIS, a free and open source geospatial program, opens in seconds, whereas in Windows it took much longer, perhaps minutes. 

A downside, a this could be the fault of the older laptop (it's about 8 years old now) I could never get the touchscreen to work, actually testing a touchscreen installation made the laptop crash and I ended up removing it. Also wifi disconnects if I close the laptop and reopen without shutting it down. I then have to reboot and wifi comes back. I tried numerous fixes for this, none that worked. It's ok, and shutting the laptop down after use is probably a good idea anyway since the bootup takes a fraction of the time of windows.

:::{hint} Run a Linux Headless Server
:class: dropdown

Linux is the perfect OS for running a headless server in your local network, in particular, using Debian server. It's easy to install on an old pc or laptop (or run on a used PC), runs efficiently, and you can run servers in Docker containers or on their own. A great example is CasaOS, that once installed can be accessed in any browser with the server's IP address and locahost and let's you run a cloud file backup and install containerized apps..
:::

## Killing Windows
The new PC arrived, a shiny (and tiny) Geekom A8 with AMD ryzen 7. Not the shiniest/fastest model, but moderately fast. It came with Windows 11 installed. I opted for Manjaro KDE Plasma on the recommendation of a colleague and it looked like a great system for it's OS approach. It was extremely satisfying to delete windows during the installation, but the install was not hiccup free especially when the pc wasn't recognizing the wireless keyboard and displays I had, and I had to do a couple of keyboard direct plug in workarounds. 

The latter continued to plague use where the wireless Logitech keyboard (which worked great in Windows!) had issues connecting to bluetooth. Sometimes bluetooth connection issues feel like giving a Powerpoint presentation in the 90s where it was always a challenge to connect to a projector. Anyway, I swapped out that beleved keyboard for one that's almost as good but that connects flawlessly everytime I use the PC. 

kept windows on old pc, but deleted a lot of extra stuff
pc w/o screen or keyboard was a challenge for installation

## Test case
Trip to CA with windows laptop and it worked flawlessly, didn't miss windows

Some key software to help you make the leap
1. Only office
2. QGIS
3. Konsole and ZSH
4. Kate
5. VS Code

## Pros/cons

{numref}`sum_table` outlines the pluses and deltas for using the Linux os across different machines.

QGIS opens in seconds, even on the older laptop

:::{table} Summary of pros and cons for using the Linux OS instead of Windows
:label: sum_table

| PROS | CONS  |
| :--------------- | :---------- |
| 🟢 Just works | 🟡 A little like living in a foreign country |
| 🟢 New and innovative solutions like auto-tiling | 🟡 Hardware compability |
| 🟢 Living in the terminal more (a suprirse pro) | 🟡 Constant updates |
| 🟢 Machines run well and apps are fast | 🟡 Bluetooth, touchscreen issues |  
| 🟢 Learning curve |🟡 Learning curve | 

:::

# Recommendations
- **Old laptop install first**. Try Linux out first on an old laptop or PC to see what OS you like. Linux distributions (called distros those in the know) such as Mint, Debian, Ubuntu, Fedora, and PopOS are great for beginners or those that want a system similar to Mac or Windows.
- **Hardware compatibility**. Be aware that some hardware may not be compatible and have backup. Better yet, install on a laptop where most things like screen and keyboard are built in.
- **Troubleshoot**. Don't be deterred when the install and use doesn't work at first. There are loads of communities online to help you out or to research solutions.
- **Embrace the terminal**. You might feel uneasy using the terminal at first, but go open it every day, practice some commands, use it to copy or re-name files. It will soon become second nature and in a few month's time you won't believe it when you go in the terminal to look for files or to complete tasks. Again, lots of information online with helpful common commands for Linux users articles easy to find.
- **Keep a backup Windows PC**. I did this because ArcGIS Pro isn't available in Linux and I use it a lot for geospatial analysis. There are alternatives such as QGIS and now GeoLibre that are making my use of Arc less and less, but it's useful to have for certain types of analyses. 
- **MS Office**. You might miss some Microsoft products like word, excel, and powerpoint, but OnlyOffice is worth installing because it can read and open any files created in MS Office and does a lot of things that Office can do. I almost never use Word anymore unless it's collaboration on a project with colleagues using word (have replaced with markdown, VS Code and OnlyOffice). I still use certain elements of Excel, probably because I haven't yet explored the spreadsheet functionality in OnlyOffice and I'm familiar with certain formulas, power query, and pivot tables in Excel. I have started to replace a lot of Excel charting and analysis features, however with Python and find the script replicability to be more dependable once set up. Note that most Linux OS's ship with LibreOffice, which is ok, but I've found OnlyOffice to be much more functional.
- **Experiment**. Try out new apps and experiment. It's kinda fun and may remind you of how fun it was when you first started using computers.

# Hardware
1. PopOS running on a Microsoft Surface Laptop
2. Raspberry Pi 5 running as a lab for cloud software
3. Geekom A8 running Manjaro Plasma KDE
4. Dell Optiplex 7020 running Debian server