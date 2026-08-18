---
title: Linux OS vs Windows
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
  Working with linux machines
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
My Windows laptop (I'm aware of the irony) ended up with Cosmic Popos, which is a great operating system built by the folks at System76. It has nice shortcuts, runs well, has cool features like auto tiling. QGIS, a free and open source geospatial program, opens in seconds, whereas in Windows it took much longer, perhaps minutes. 

A downside, a this could be the fault of the older laptop (it's about 8 years old now) I could never get the touchscreen to work, actually testing a touchscreen installation made the laptop crash and I ended up removing it. Also wifi disconnects if I close the laptop and reopen without shutting it down. I then have to reboot and wifi comes back. I tried numerous fixes for this, none that worked. It's ok, and shutting the laptop down after use is probably a good idea anyway since the bootup takes a fraction of the time of windows.

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
:alignment: center

| PROS | CONS  |
| :--------------- | :---------- |
| 🟢 Just works | 🟡 A little like living in a foreign country |
| 🟢 New and innovative solutions like auto-tiling | 🟡 Hardware compability |
| 🟢 Living in the terminal more (a suprirse pro) | 🟡 Constant updates |
| 🟢 Machines run well and apps are fast | 🟡 Bluetooth, touchscreen issues |  
| 🟢 Learning curve |🟡 Learning curve | 

:::

# Recommendations
- Try Linux out first on an old laptop

# Hardware details