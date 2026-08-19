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
  Switching from Windows to Linux for daily work is a worthwhile and often valuable consideration. I describe my personal journey to change motivated by persistent performance frustrations with Windows 11. I converted one laptop and a mini-PC—one running Cosmic Pop!_OS and the other running Manjaro KDE Plasma—alongside a headless Debian server. Key benefits include significantly faster application startup times and an overall sense that machines run more efficiently under Linux. The author also acknowledges challenges such as Bluetooth connectivity, touchscreen compatibility, and the learning curve of terminal-based workflows, along with practical workarounds. Recommendations for prospective switchers include starting on old hardware, embracing the terminal, using alternatives like OnlyOffice and VS Code, and maintaining a backup Windows machine for software that lacks Linux support. A summary table of pros and cons is provided.
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
Nearly two years ago, I became very frustrated with Windows 11 on a Dell XPS laptop I used for work. It would get particularly bad when Windows Defender would run in the middle of the mornig, rendering my mouse, some programs, and making everything exceptionally slow for about an hour. I tried everything to reschedule the scans, from turning it off to turning it back on, but it kept running at inopportune moments, like it had a mind of its own.

I had been thinking about switching my main work pc to Linux at the time, and one morning when Defender was really bad, I ordered a new PC. I had been experimenting with Linux Mint and Ubuntu on an old laptop that didn't have enough memory to install Windows 11, and both OS's brought new life to the machine, running quickly and operating like a PC should: for you!

# Changing to Linux
My Microsoft Surface laptop (I'm aware of the irony) ended up with Cosmic Popos, which is a great operating system built by the folks at System76. It has nice shortcuts, runs well, and includes cool features like auto-tiling. QGIS, a free and open source geospatial program, opens in seconds, whereas in Windows it took much longer, perhaps minutes. 

:::{important} Installing Pop!_OS
:class: dropdown

Here are the steps to replace Windows and install Linux with Pop!_OS from system76. There are hundreds of YouTube videos on how to install Linux, so if you get stuck, check them out.

1.  Download Pop!_OS ISO
- Go to the [Pop!_OS installation](https://system76.com/support/install-pop/). The instructions are great and to the point.
- Download the ISO file
2.  Download Rufus
- Go to rufus.ie (https://rufus.ie)
- Download the Windows version
3. Prepare USB Drive
- Plug in a USB flash drive
- Open Rufus and select your USB drive
- Select the Pop!_OS ISO file
- Click "Start" to flash the ISO to the USB
- Wait for the process to complete
- Safely eject the USB
4. Boot from USB
- Shut down the target PC
- Plug in the USB drive
- Power on and press the boot menu key (Escape, F10, F2. Look up the specific button to enter as a search online)
- Select the USB drive from the boot menu
- Press Enter to boot in normal mode
5. Install Pop!_OS
- Select your language → Click "Clean Install"
- Select the internal drive (not the USB)
- Set up user account (name, username, password)
- Enable full disk encryption if desired (recommended)
- Click "Encrypt" → Set encryption password
- Wait for installation to complete
- Click "Restart Device"
- Remove USB when the BIOS screen appears on reboot
6. Initial Setup
- Enter decryption password (if encryption enabled)
- Log in with your password
- Complete the Cosmic Desktop setup wizard:
- Accessibility options (skip if not needed)
- Connect to Wi-Fi
- Select language and keyboard layout
- Set time zone
- Choose color scheme and panel layout
- Click "Finish"

You may want to install the software you need at this point. As mentioned below, I recommend removing LibreOffice and replacing it with OnlyOffice, replacing the terminal with Konsole, and installing ZSH and Oh My ZSH.
:::

A downside, a this could be the fault of the older laptop (it's about 8 years old now) I could never get the touchscreen to work, actually testing a touchscreen installation made the laptop crash and I ended up removing it. Also, Wi-Fi disconnects if I close the laptop and reopen without shutting it down. Then I have to reboot, and the Wi-Fi comes back. I tried numerous fixes for this, none of which worked. It's ok, and shutting the laptop down after use is probably a good idea anyway since the bootup takes a fraction of the time of Windows.

:::{hint} Run a Linux Headless Server
:class: dropdown

Linux is the perfect OS for running a headless server on your local network, especially Debian Server. It's easy to install on an old pc or laptop (or run on a used PC), runs efficiently, and you can run servers in Docker containers or on their own. A great example is CasaOS, which you can access in any browser using the server's IP address or localhost, and it lets you run cloud file backups and install containerized apps. Here are the installation steps, along with a bonus CasaOS installation to get you started. This is adapted from the [To Thrifinity & Beyond](https://www.youtube.com/watch?v=Z4NUspx5sho&t=183s) youtube video:

1. Gather Required Items
- Old computer (e.g., Dell Optiplex 3020)
- USB stick with Debian 13 image
- Monitor, keyboard, and mouse (temporarily)
2. Configure BIOS
- Enter BIOS (F2, F10, Escape. Look up the BIOS sequence to enter when booting for your specific machine)
- Disable Secure Boot
- Set boot order to start with USB
3. Launch Installer
- Boot from USB drive
- Select "Graphical Install"
4. Set Up Basic Configuration
- Select language and region
- Name your server
- Set network name (e.g., "local")
- Create a username and password
- Select time zone
5. Partition Disk
- Choose "Full Disk" installation
- Select internal hard drive (not USB)
- Confirm and continue
6. Configure Package Manager
- Download from debian.org
- Leave proxy empty
- Click "No" on data sharing
7. Select Software
- Uncheck everything except:
- SSH server
- Standard system utilities
- Click "Continue"
8. Reboot and Log In
- Remove USB before reboot
- Log in with your username and password
9. Go Headless
- Unplug monitor, keyboard, and mouse
- SSH into server from another computer:
ssh your_username@192.168.1.XXX
- Enter your password when prompted
10. Update System
- Run:
sudo apt update && sudo apt upgrade -y
11. Install CasaOS
- Run:
curl -fsSL https://get.cas.io | sudo bash
12. Access CasaOS Dashboard
- Open a browser and navigate to:
http://192.168.1.XXX
- Complete CasaOS setup
- Install apps like Plex, Minecraft server, and others
:::

## Killing Windows
The new PC arrived, a shiny (and tiny) Geekom A8 with AMD Ryzen 7. Not the shiniest/fastest model, but moderately fast. It came with Windows 11 installed. I opted for Manjaro KDE Plasma on a colleague's recommendation, and it looked like a great system for its OS approach. It was extremely satisfying to delete Windows during installation, but the install wasn't hiccup-free, especially when the PC wasn't recognizing my wireless keyboard and displays, and I had to do a couple of direct plug-in keyboard workarounds. 

The latter continued to plague use where the wireless Logitech keyboard (which worked great in Windows!) had issues connecting to Bluetooth. Sometimes Bluetooth connection issues feel like giving a PowerPoint presentation in the 90s where it was always a challenge to connect to a projector. Anyway, I swapped out that beleved keyboard for one that's almost as good, but that connects flawlessly every time I use the PC. 

Kept Windows on old pc, but deleted a lot of extra stuff
pc w/o screen or keyboard was a challenge for installation

## Test case
Trip to CA with Windows laptop and it worked flawlessly, didn't miss Windows

## Key Software
Some key software to help you make the leap
1. OnlyOffice
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
| 🟢 Living in the terminal more | 🟡 Constant updates |
| 🟢 Machines run well and apps are fast | 🟡 Bluetooth, touchscreen issues |  
| 🟢 Learning curve |🟡 Learning curve | 

:::

# Recommendations
- **Try it out on an old laptop**. Try Linux out first on an old laptop or PC to see what OS you like. Linux distributions (called distros by those in the know) such as Mint, Debian, Ubuntu, Fedora, and Pop! _ OS are great for beginners or anyone who wants a system similar to Mac or Windows.
- **Hardware compatibility**. Be aware that some hardware may not be compatible, and have a backup plan. Better yet, install it on a laptop where most things, like the screen and keyboard, are built in.
- **Troubleshoot**. Don't be deterred when the install and use don't work at first. There are loads of communities online to help you out or to research solutions.
- **Embrace the terminal**. You might feel uneasy using the terminal at first, but go open it every day, practice some commands, and use it to copy or rename files. It will soon become second nature, and in a few months you won't believe it when you go into the terminal to look for files or complete tasks. Again, lots of information online with helpful common commands for Linux users; articles are easy to find.
- **Keep a backup Windows PC**. I did this because ArcGIS Pro isn't available in Linux and I use it a lot for geospatial analysis. Alternatives like QGIS and now GeoLibre are reducing my use of Arc, but it's still useful for certain types of analyses. 
- **MS Office**. You might miss some Microsoft products like Word, Excel, and PowerPoint, but OnlyOffice is worth installing because it can read and open any files created in MS Office and does a lot of things that Office can do. I almost never use Word anymore unless I'm collaborating on a project with colleagues who use Word (I've replaced it with Markdown, VS Code, and OnlyOffice). I still use certain elements of Excel, probably because I haven't yet explored the spreadsheet functionality in OnlyOffice and I'm familiar with certain formulas, power query, and pivot tables in Excel. I have started replacing a lot of Excel charting and analysis features with Python, and I find the script replicability more dependable once set up. Most Linux OSs ship with LibreOffice, which is ok, but I've found OnlyOffice much more functional.
- **Experiment**. Try out new apps and experiment. It's kinda fun and may remind you of how fun it was when you first started using computers.

# Hardware
The current general hardware I'm using without all the details is the following:

1. PopOS running on a Microsoft Surface Laptop.
2. Raspberry Pi 5 running as a lab for cloud software.
3. Geekom A8 running Manjaro Plasma KDE.
4. Dell Optiplex 7020 running Debian server.