---
title: Linux vs. Windows
subject: Hardware
subtitle: Time to take the plunge!
short_title: Linux
date: 2026-08-25
authors:
  - name: Vance Russell
    affiliations: 
      - 3point.xyz
    email: vance@3point.xyz
license: CC-BY-4.0
keywords: hardware, efficiency, linux, windows, os
abstract: |
  Not the most exciting topic for some, but what OS you use affects you nearly every single day. Switching from Windows to Linux for everyday use is not only worthwhile but, in many cases, also valuable. My experience switching systems came from continual frustrations with Windows 11 performance. I have tried 5 different distros so far and like two in particular. The main Linux advantages are open-source software, much faster application start-up times, and a general feeling that computers run more efficiently. There are difficulties, such as Bluetooth connectivity problems, touchscreen compatibility issues, and the learning curve of terminal-based workflows. Recommendations include beginning with older hardware, being patient with hardware incompatibility, using the terminal more, and looking for MS Office alternatives. A summary table of Linux advantages and disadvantages is included.
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

> "These are tools. I mean, modern dentistry is great. But your dentist doesn't insist you worship him." Paulina Borsook

# Frustration & Move
Operating systems are (not) the most exciting thing in the world, but like plumbing, electricity, and other infrastructure or tools, they need to work. The operating system your computer uses affects you every day; that's a lot of time if your OS doesn't work for you. About two years ago, I became very frustrated with Windows 11 on a Dell XPS laptop I used for work. It got particularly bad when Windows Defender ran in the middle of the morning, rendering my mouse and some programs unusable and slowing the laptop to the point of being unusable. I tried everything to reschedule the scans, or even turning Defender off, but it kept running at inopportune moments, like it had a mind of its own. Defender was only one of the issues, and I started noticing that Windows just seemed a bit slow, tired, and old.

I had been thinking about switching my main work PC to Linux at the time. One morning, when Defender was really bad, I installed Ubuntu on an older laptop that Windows had bogged down. It worked flawlessly and brought new life into the laptop. That experience immediately convinced me to purchase a new pc and install a fresh Linux distro. This way I could pare down apps on the "old" laptop but still run some apps not available in Linux such as ArcGIS.

## Killing Windows
The new PC arrived, a shiny (and tiny) Geekom A8 with AMD Ryzen 7. It came with Windows 11 installed. I opted to install Manjaro KDE Plasma on a colleague's recommendation. It was extremely satisfying to delete Windows during installation,. I can't say the install was hiccup-free, the PC/Manjaro wouldn't recognize wireless keyboards and I had to plug one in to complete the setup, but once around those obstacles, it was up and running. 

I immmediately noticed how zippy it was, due in part, to the new unemcumbered PC, but most everything just ran smoothly. The bluetooth wireless hardware issue continued to plague me, however, which led to purchasing a Linux specific keyboard. Aside: Sometimes Bluetooth connection issues feel like giving a PowerPoint presentation in the 90s, when connecting to a projector was always a challenge. 

Once swapped out the new keyboard worked well. I ended up not swapping out a Logitech vertical mouse and just plugged it into a usb cable. Not ideal, but in reality those were leftover hardware items from using Windows.

# Nuts & bolts
The laptop where I initially installed Ubuntu is a Microsoft Surface laptop (I'm aware of the irony). After trying out Ubuntu and Mint on it, I switched to Pop!_OS, a great operating system built by the folks at System76. Pop!_OS, which is impossible to type out rapidly, has nice shortcuts, runs without issues, and includes cool features like auto-tiling. QGIS, a free and open source geospatial program, opens in seconds, whereas in Windows it took much longer, perhaps minutes. On the laptop there were still some software issues such as closing the laptop disconnecting from wifi until I rebooted and not being able to use the touchscreen (I tried to make it work, never succeeded). 

## Installation
Installing Linux is straightforward (see the Installing Pop!_OS dropdown below). Aside from creating a bootable USB, a key part of the installation is diving into the BIOS, which can be frustrating to access and feel like a trip back to the 20th century. See {numref}`bios` to find the BIOS key and boot menu key for your hardware. Don't give up after one try; it often takes multiple attempts and repeated correct key presses.

:::{important} Installing Pop!_OS
:class: dropdown

Here are the steps to replace Windows and install Pop!_OS from System76. There are hundreds of YouTube videos on how to install Linux, so if you get stuck, check them out.

1.  Download Pop!_OS ISO
  - Go to the [Pop!_OS installation](https://system76.com/support/install-pop/). The instructions are great and to the point.
  - Download the ISO file
2.  Download Rufus
  - Go to the Rufus website: https://rufus.ie
  - Download the Windows version
3. Prepare USB Drive
  - Plug in a USB flash drive
  - Open Rufus and select your USB drive
  - Select the Pop!_OS ISO file
  - Click "Start" to flash the ISO to the USB
  - Wait for the process to complete
  - Safely eject the USB
4. Boot from USB
  - Open the BIOS menu for your machine (see {numref}`bios`). Disable secure boot under security, and under boot or boot sequence, change the order so that it boots from USB first
  - Shut down the target PC
  - Plug in the USB drive
  - Power on and press the boot menu key (see {numref}`bios`)
  - Select the USB drive with the ISO file on it from the boot menu
  - Press Enter to boot in normal mode
5. Install Pop!_OS
  - Select your language → Click "Clean Install"
  - Select the internal drive (not the USB)
  - Set up user account (name, username, password)
  - Enable full disk encryption if desired (recommended)
  - Click "Encrypt" → Set encryption password
  - Wait for installation to complete
  - Remove the USB from the PC/laptop
  - Click "Restart Device"
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
  - Install your software
:::

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

## Linux Server
Another useful approach is creating a Linux server. This is especially useful for creating a cloud-based file system, developing a map server using GeoLens or QGIS, or creating a virtual machine or containerized server. Debian Server is well known for this role because of its stability and ease of installation. See the "Running a Headless Server" pulldown below to get started.

:::{hint} Run a Linux Headless Server
:class: dropdown

Linux is the perfect OS for running a headless server on your local network, especially Debian Server. It's easy to install on an old pc or laptop (or run on a used PC), runs efficiently, and you can run servers in Docker containers or on their own. A great example is CasaOS, which you can access in any browser using the server's IP address or localhost, and it lets you run cloud file backups and install containerized apps. Here are the installation steps, along with a bonus CasaOS installation to get you started. This is adapted from the [To Thrifinity & Beyond](https://www.youtube.com/watch?v=Z4NUspx5sho&t=183s) youtube video:

1. Gather Required Items
  - Old or new computer
  - USB stick with Debian 13 image. Go to the [Debian](https://www.debian.org) site to download
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
  - Run: `sudo apt update && sudo apt upgrade -y` in the terminal
11. Install CasaOS
- Run: `curl -fsSL https://get.casaos.io | sudo bash` in the terminal
12. Access the CasaOS Dashboard
  - Open a browser and navigate to: http://192.168.1.XXX
  - Set username and password
  - Install apps like Plex, Minecraft server, and others
:::

## Key Software
Software recommendatons to help you make the leap includes the following:
1. **OnlyOffice**. A nice replacement for MS Office that runs the same files with Office extensions. Some limited functionality is noticeable such as no power queries in Excel. Really like the tab based approach to files, e.g., you open OnlyOffice and can a spreadsheet and doc open in different tabs.
2. **QGIS**. If you do any geospatial analysis, QGIS works very well in Linux.
3. **Konsole**. Konsole comes with Manjaro, but not Debian or Ubuntu. You might want to check it out after using the terminal that came with your install.
4. **Kate**. Really great text editor that can also be used as an IDE.
5. **VS Code**. Visual Studio Code is the IDE that everyone uses. Some people recommend VSCodium, which is the same open-source editor as VS Code but without telemetry/tracking.

# Pros/cons
{numref}`sum_table` outlines the pluses and deltas of using Linux across different machines. You'll notice speed with the clean install, especially on software that takes much longer to open in Windows. You'll likely find that working in Linux at first is like living in a foreign country. You'll immediately like some things and miss others. You're OS bilingual now, so you can always return to Windows for the things you like there.

:::{table} Summary of pros and cons for using the Linux OS instead of Windows. Note that living in a foreign country is both a pro and a con; you'll always like and dislike things anywhere.
:label: sum_table

| PROS | CONS  |
| :--------------- | :---------- |
| 🟢 Living in a foreign country | 🟡 Living in a foreign country |
| 🟢 New and innovative solutions like auto-tiling | 🟡 Hardware compatibility |
| 🟢 Open source | 🟡 Constant updates |
| 🟢 Machines run well and apps are fast | 🟡 Bluetooth, touchscreen issues |  
| 🟢 Learning curve |🟡 Learning curve | 

:::

# Recommendations
- **Try it on an old laptop**. Try Linux out first on an old laptop or PC to see what OS you like. Linux distributions (called distros by those in the know) such as Mint, Debian, Ubuntu, Fedora, and Pop!_OS are great for beginners or anyone who wants a system similar to Mac or Windows.
- **Consider ardware compatibility**. Be aware that some hardware may not be compatible, and have a backup when something doesn't work. Better yet, install Linux on a laptop where most things, like the screen and keyboard, are built in and there's less likelihood for incompatibility especially for wireless bluetooth connected hardware.
- **Troubleshoot**. Don't be deterred when the install doesn't fully work, or something fails. There are loads of communities online to help you out or to research solutions. Remember, switching over at first can be experimental, especially if you keep a Windows backup, just in case!
- **Embrace the terminal**. You might feel uneasy using the terminal at first, but one of the best early Linux pieces of advice I received was to try to use the terminal every day, even for simple things like viewing or copying files. Using it will soon become second nature, and in a few months you won't believe it when you open the terminal to find files or complete tasks. Again, lots of information online with helpful common commands for Linux users; articles are easy to find.
- **Keep a backup Windows PC**. I did this because ArcGIS Pro isn't available in Linux and I use it for geospatial analysis. Alternatives like QGIS and now GeoLibre are reducing my use of Arc, but it's still useful for certain types of analyses. 
- **Use OnlyOffice**. You might miss some Microsoft products like Word, Excel, and PowerPoint. OnlyOffice is worth installing because it can read and open any files created in MS Office and does a lot of what Office can do, with a similar user interface.
- **Experiment**. Check out new apps and experiment; try tiling, a new workflow, or a different file structure. It's kinda fun and may remind you of how fun it was when you first started using computers.

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
5. An ancient Lenovo laptop that creaked along was revived by Pop!_OS and is now testing Mainstream OS.

Of the distros I've tried, I've had the fewest issues with Pop!_OS, although I really like some Manjaro features. The Mainstream OS is pretty cool, but I've only used it for a couple of days. The laptop it is running on has 2 mb of RAM and very little storage. I'm considering trying a minimalist distro, like antiX, just to see what a minimal setup looks like and whether it runs faster on a more limited machine.