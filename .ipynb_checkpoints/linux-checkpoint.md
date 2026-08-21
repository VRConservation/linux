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
  Not the most exciting topic for some, but it affects nearly every single day at work. Switching from Windows to Linux for everyday use is not only worthwhile but, in many cases, also valuable. My experience switching systems came from continual frustrations with Windows 11 performance. I have converted one laptop and a small PC—one running Cosmic Pop!_OS and the other using Manjaro KDE Plasma—as well as a headless Debian server. The main advantages are much faster application start-up times and a general feeling that the computers run more efficiently on Linux. There are difficulties, such as Bluetooth connectivity problems, touchscreen compatibility issues, and the learning curve of terminal-based workflows, along with practical solutions. Recommendations include beginning with older hardware, being patient with hardware incompatibility, using the terminal more, and looking for MS Office alternatives. A summary table of the advantages and disadvantages is included.
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

:::{figure} linuxmove.png
:alt: Linux move from Windows
:::

# Moving to Linux
I admit it, this isn't the most exciting topic for some folks, but what operating system your computer uses affects you every day at work, which is a lot of time. Nearly two years ago, I became very frustrated with Windows 11 on a Dell XPS laptop I used for work. It got particularly bad when Windows Defender ran in the middle of the morning, rendering my mouse and some programs unusable and slowing the laptop to the point of being nearly unusable. I tried everything to reschedule the scans, or even turning Defender off, but it kept running at inopportune moments, like it had a mind of its own.

I had been thinking about switching my main work PC to Linux at the time, and one morning, when Defender was really bad, I experimented with an Ubuntu install on an older laptop, which brought new life to a machine that was bogged down even running Windows 10. That convinced me to pare down the software on the XPS, buy a mini-PC, and do a fresh install with a Linux OS.

# Nuts & bolts
My Microsoft Surface laptop (I'm aware of the irony) ended up running Cosmic Pop!_OS, a great operating system built by the folks at System76. It has nice shortcuts, runs well, and includes cool features like auto-tiling. QGIS, a free and open source geospatial program, opens in seconds, whereas in Windows it took much longer, perhaps minutes. A key part of change is diving into BIOS and boot menus. See {numref}`bios` to find the BIOS key and boot menu key for your hardware.

:::{table} Quick reference guide for BIOS setup and boot menu keys
:label: bios

| Brand | BIOS Key | Boot Menu Key |
| :---- | :------- | :----------- |
| Acer | F2 | F12 |
| ASUS | F2 | Esc |
| Dell | F2 | F12 |
| HP | F2 | F12 |
| Lenovo | F1 or F2  | F12 |
| Microsoft | Vol Up + Power | Vol Down + Power |
| Toshiba | F2 | F12 |

:::

:::{important} Installing Pop!_OS
:class: dropdown

Here are the steps to replace Windows and install Pop!_OS from System76. There are hundreds of YouTube videos on how to install Linux, so if you get stuck, check them out.

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

You may want to install the software you need now. As mentioned below, I recommend removing LibreOffice and replacing it with OnlyOffice, replacing the terminal with Konsole, and installing ZSH and Oh My ZSH.
:::

A downside, a this could be the fault of the older laptop (it's about 8 years old now) I could never get the touchscreen to work, actually testing a touchscreen installation made the laptop crash and I ended up removing it. Also, Wi-Fi disconnects if I close the laptop and reopen without shutting it down. Then I have to reboot, and the Wi-Fi comes back. I tried numerous fixes, but none worked. It's OK, and shutting the laptop down after use is probably a good idea anyway since the bootup takes a fraction of the time Windows takes.

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
ssh your_username@192.168.1.XXX (enter actual IP address after the @)
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
The new PC arrived, a shiny (and tiny) Geekom A8 with AMD Ryzen 7. Not the shiniest/fastest model, but moderately fast. It came with Windows 11 installed. I opted for Manjaro KDE Plasma on a colleague's recommendation, and it looked like a great system for its OS approach. It was extremely satisfying to delete Windows during installation, but the install wasn't hiccup-free, especially when the PC didn't recognize my wireless keyboard and displays, and I had to use a couple of direct plug-in keyboard workarounds. 

The latter continued to plague use where the wireless Logitech keyboard (which worked great in Windows!) had issues connecting to Bluetooth. Sometimes Bluetooth connection issues feel like giving a PowerPoint presentation in the 90s where it was always a challenge to connect to a projector. Anyway, I swapped out that beleved keyboard for one that's almost as good, but that connects flawlessly every time I use the PC. 

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
| 🟢 New and innovative solutions like auto-tiling | 🟡 Hardware compatibility |
| 🟢 Living in the terminal more | 🟡 Constant updates |
| 🟢 Machines run well and apps are fast | 🟡 Bluetooth, touchscreen issues |  
| 🟢 Learning curve |🟡 Learning curve | 

:::

# Recommendations
- **Try it out on an old laptop**. Try Linux out first on an old laptop or PC to see what OS you like. Linux distributions (called distros by those in the know) such as Mint, Debian, Ubuntu, Fedora, and Pop! _ OS are great for beginners or anyone who wants a system similar to Mac or Windows.
- **Hardware compatibility**. Be aware that some hardware may not be compatible, and have a backup plan. Better yet, install it on a laptop where most things, like the screen and keyboard, are built in.
- **Troubleshoot**. Don't be deterred when the install and use don't work at first. There are loads of communities online to help you out or to research solutions.
- **Embrace the terminal**. You might feel uneasy using the terminal at first, but go open it every day, practice some commands, and use it to copy or rename files. It will soon become second nature, and in a few months you won't believe it when you open the terminal to find files or complete tasks. Again, lots of information online with helpful common commands for Linux users; articles are easy to find.
- **Keep a backup Windows PC**. I did this because ArcGIS Pro isn't available in Linux and I use it for geospatial analysis. Alternatives like QGIS and now GeoLibre are reducing my use of Arc, but it's still useful for certain types of analyses. 
- **MS Office**. You might miss some Microsoft products like Word, Excel, and PowerPoint. OnlyOffice is worth installing because it can read and open any files created in MS Office and does a lot of what Office can do, with a similar user interface. I almost never use Word anymore unless I'm collaborating on a project with colleagues who use Word (I've replaced it with Markdown, VS Code, and OnlyOffice). I still use certain elements of Excel, probably because I haven't explored OnlyOffice's spreadsheet functionality and I'm familiar with Excel functions/features. I have started replacing a lot of Excel charting and analysis features with Python, and I find the script replicability more dependable once set up.
- **Experiment**. Try out new apps and experiment. It's kinda fun and may remind you of how fun it was when you first started using computers.

# Resources
The Linux community generally is awesome and very helpful, so there are a lot of resources out there. So much that it can be hard to wade through. Here are a couple of resources you may find useful:

1. [Introduction to Linux](https://www.youtube.com/watch?v=sWbUDq4S6Y8). A comprehensive course from freeCodeCamp.org on using Linux for beginners. Six hours of nearly everything you need to know.
2. [Manjaro Linux Tutorials](https://www.youtube.com/watch?v=TN_xsd92XpI&list=PLAxJ4-o7ZoPcGbgcOikBiooM15cbdQta1). Set of excellent tutorials from Qiusheng Wu on installing Manjaro on your computer. One item that stood out to me was using shell scripts to automate software installation during setup. This makes switching distros or reinstalling quick and avoids downloading each software package you use. 
3. [Download Ubuntu & Create Bootable USB](https://www.youtube.com/watch?v=AB0lXpoql7s). This video is simple and to the point about creating a bootable USB drive to install Linux.

## Appendix: Hardware
For what it's worth, here are the general software installations I have running with PC's I own:

1. Pop!_OS running on a Microsoft Surface Laptop.
2. Raspberry Pi 5 running as a lab for cloud software.
3. Geekom A8 running Manjaro Plasma KDE.
4. Dell Optiplex 7020 running Debian server.
5. An ancient rose-gold Lenovo laptop that creaked along was revived by Pop!_OS and is now testing Mainstream OS.