Title: Glanceable Displays: Installing Raspbian on a Raspberry Pi
Date: 2019-07-21
Category: Technology
Tags: Glanceable Displays
Status: published
Series: Glanceable Displays
series_index: 2

## Preface

This is the second article in a series about Glanceable Displays and my efforts to create
one for my household.  For other articles in the series, click on the title of the article
under the heading "Glanceable Displays" on the right side of the webpage.

## Introduction

[TOC]

The methods detailed in this article provide for simple installation of the Raspbian
operating system using the
[New Out Of Box Software (NOOBS)](https://www.raspberrypi.org/documentation/installation/noobs.md)
installation method, as suggested for beginners by the
[Raspberry Pi site](https://www.raspberrypi.org).  While there are more direct methods
for experienced users, the NOOBs installation was selected for it's simplicity and ease of
installation.

Using the NOOBs installation, this article details the first steps I took in setting up one of
my Raspberry Pi systems to be a glanceable display for my family.  Those steps start with the
formatting of a MicroSD card and installation of the NOOBs installer on to that MicroSD card.
After installing that card into the Raspberry Pi, the steps continue with the installation
of a stock Raspbian distribution, detailing the a couple of questions that need to be answered
to complete the installation.  Finally, to enable remote access, the last step is to ensure
that I can access the Raspberry Pi using SSH for later configuration and control.

## Requirements

- Raspberry Pi, version 3.0 or later
- Power Supply for Raspberry Pi
- Keyboard and Mouse
- HDMI cable connected to monitor
- Cat5 Ethernet cable

!!! note
    Please keep your own notes as you go, and refer back to them.  While I have tested the steps on my own Raspberry Pi machines, they were by no means exhaustive tests.

## Step 1: Interfacing With a MicroSD Card

The configuration and main drive for a Raspberry Pi is a MicroSD card.  To get the card
ready for use, your computer must be able to interface with the card.  

Most computers do not come with MicroSD slots, but there are a fair number with SD slots.  
To make things easier for MicroSD buyers, some of the more high
end MicroSD makers include a MicroSD-to-SD adapter in their packaging, such as
[this 32GB MicroSD card from Amazon](https://www.amazon.com/gp/product/B06XWN9Q99).  I started
out using this, but found that the adapter was only good for 3-4 uses, not for continual use.

An alternative is a more multi-purpose adaptor, such as
[this multi-adapter from Amazon](https://www.amazon.com/gp/product/B01KFXS83W).  As it is
made from a more durable material, it will survive more uses.  The one that I bought from
Amazon at 7.00 USD is still working after about 70+ uses, so at 0.10 USD per use, it has
already paid for itself.  Also, as it has a USB adapter, I can plug it into a USB extension
cable that I already have on my desk.

Whichever way you decide to go, make sure to add the MicroSD card to the adapter before
plugging the adaptor into you computer.  Once it is securely in the adapter, make sure to
apply it to the relevant slot on your computer firmly, and make sure the connection is there.
On my Windows 10 machine, I can tell this happens as it will acknowledge the connection by
opening up an Explorer window, with either a "please format" instruction or a list of any
files in the directory.

## Step 2: Getting the MicroSD Card Ready

!!! note
    Note that the steps that follow are for my Windows 10 machine.  The
    [NOOBs site](https://www.raspberrypi.org/documentation/installation/noobs.md), has sections for installing on Mac and Linux, but I did not test them.  If they do not work,please Google/Bing `linux microsd card format` and `linux microsd card mount`. Feel free to replace the generic `linux` in the searches with the name of the Linux distribution that you are using.

### Step 2a: Reformatting a Used MicroSD Card

Reusing old hardware is important, for many reasons such as the environment and cost. To make
sure that is possible, it took me a number of tries to create a solid recipe for reformatting
the MicroSD cards.  As I mention in the `Requirements` section, keep good notes of what you
do, or if following a recipe like this one, what changes you made to the recipe.

While there is a command line only tool that will also do the job, I found it clunky and hard
to use.  Instead, the Disk Management applet for the control panel was the tool I settled on.
This can be invoked by typing `partition` in the search window on the tool bar and selecting
the `create and format hard disk partitions` item.

Selecting that item brought up the `Disk Management` window, showing a break down of
every drive connected to my computer.  When the MicroSD card was properly connected to the
computer, it showed up as Removable media after all of my permanent drives.  Using the right
mouse button, I clicked on each of the blocks on my MicroSD card and selected the
`Delete Volume` menu item until all of the volumes were gone.  When that was accomplished, I
was left with two blocks, and right clicking on the rightmost block presented me with a
`Delete Partition` menu item, which consolidated all of the partitions into a single
unallocated block.

From there, I was able to right click on the Unallocated partition to select the
`Create Volume` menu item.  This started a simple wizard that quickly walked me through
the options for creating a new volume.  I used all defaults that were presented with the
exception of the `file system` and `quick format` settings.  I changed the `file system`
setting to `FAT32` and unchecked the `Use Quick Format` checkbox, before clicking on
finish and waiting for about 30 minutes before the format was complete.

### Step 2b: Formatting a New MicroSD Card

From a Windows 10 point of view, this was easy.  When the MicroSD card was properly connected
to my computer, it prompted me to format the card, presenting me with the format dialog
itself.  When formatting the MicroSD card, it was important to select `FAT32` as the type
of format and to unselect `Quick Format` on the dialog.  Once I clicked the format button,
it took a good while before it was completed.  As a rough estimate, I guessed that it was
roughly 1 minute per gigabyte on the MicroSD card, regardless of computer speed.

## Step 3: Install Raspbian Lite Using NOOBS

!!! note
    When the format is finished from the previous step, it is important to go to your taskbar and eject the media from your computer.  I accomplished this by right clicking on the USB stick icon and selecting "Eject Mass Storage Device" from the menu.  At that point, I cleanly removed the adaptor and the MicroSD card from the computer to ensure the ejection was complete. When I tested various scenarios, any time that I forgot to eject the media at this point, it did not take later on.  

The people behind the Raspberry PI made sure there is a simple to use installation system
that simplifies the task of installing operating systems on to the Raspberry Pi.  The
[New Out Of Box Software (NOOBS)](https://www.raspberrypi.org/documentation/installation/noobs.md)
site aims to allow a fairly basic installation of Raspberry Pi operating systems with
little effort.  Unless you are familiar with Linux systems, their installation can be
very daunting, so it is best to keep the installation as simple as possible.

To start that process, I downloaded the
[NOOBS zip file](https://downloads.raspberrypi.org/NOOBS_latest) from their web site
to my computer.  After reinserting the MicroSD card and adapter to my computer, I then unzipped
the contents of the `NOOBS_V3_2_0.zip` file to the root of the drive for the MicroSD card.
I had to take care to ensure that the contents were in the root of the drive, not in a
subdirectory of the drive.  This happened enough times that I actually unzipped the files to
a local directory and just used XCOPY to copy the files over, solving the placement problem
for myself.

As with the note at the start of this section, once this action was done, I once again ejected
the USB device before disconnecting it from the computer, for the same reasons.

Taking the MicroSD card, I found the MicroSD port on the Raspberry Pi.  The port is flat with
the motherboard of the Raspberry Pi, and the cases I have all have a hole in the case to
make it easy to find.  Inserting the card into the port, I then attached the other cables for
monitor (HDMI), ethernet (Cat5), keyboard (USB), and mouse (USB), with the 5V adapter cable
being last.

Two minutes later, I was presented with a screen which prompted me to select the operating
system to install.  I tried a number of times to get the `Raspbian Lite` install to work, but
encountered a number of issues, so I defaulted to the stock `Raspbian [RECOMMENDED]` install.
Once I made this choice, I selected `Raspbian [RECOMMENDED]` from the top of the list in the
NOOBs installation dialog, followed by pressing the `Install` button at the top.  From there,
it took about 30 minutes or so before I was prompted with a dialog box that said:

```text
OS(es) installed successfully
```

When I pressed the `OK` button on that dialog, the system rebooted with first a rainbow
screen, then a screen with a big raspberry on it, then lots of text scrolling by quickly.
After a relatively small amount of action and a lot of waiting, it was now time to set up
the operating system for simple uses!

## Step 4: Initial System Setup

There was a lot of text that scrolled by so quickly, I was unable to read it.  From what
I could see, there were a lot of green OK texts on the left side, so I guessed that the
installation had succeeded.  After a nice round of blinking lights from the Raspberry Pi,
the desktop showed up and proceeded to walk me through the setup configuration.

The first dialog was pretty simple, with the title `Welcome to Raspberry Pi`.  The important
thing to note off of this dialog is at the bottom right of the dialog is the IP address that
the system currently has assigned to it.  As this was important, I wrote it down, and
proceeded with the rest of the configuration.  

The configuration is a series of simple dialogs, each giving a clear indication of what is
required.  Whenever I pressed the `Next` button, it wrote the information to the system
configuration files.  As such, I expect delays between when I pressed the `Next` button and
when the next dialog showed up.  Turns out that was a rather healthy expectation.

Some of the things that were setup were:

- country
- language
- time zone
- setting a new password
- take care of black border
- update software

Having tested this workflow, I knew that the next workflow for my glanceable display would
include updating existing packages and installing new packages.  As such, I skipped the
update software, knowing I would do it later.  Both paths produce the same results, so feel
free to skip it like I did, or update at a later point.  

!!! warning
    If you forget the password that you change it to, there is no easy way to recover what you changed the password to.  Consider creating a *fake* entry in a password manager, like LastPass, and storing the password there for later use.

## Step 5: Setting Up SSH Access

That being accomplished, the last thing to complete before stopping the installation of the
bare bones system was to enable SSH access. By enabling SSH access, I could sit at my
comfortable workspace, using my normal computer, chair, and desk instead of at the workbench
where I had the Raspberry Pi connected.  Frankly, the computer was connected in an almost
Frankenstein like mess of wires on an old desk with a chair that was normally reserved for
people visiting, not typing. My own workspace looked very inviting.

To enable access, I entered the command `sudo raspi-config`, selecting
`5. Interfacing Options`, then selecting `P2 SSH`, and finally answering Yes to the question
`Would you like the SSH server to be enabled?`.  After this, the computer took about 30
seconds before being responsive again, with the text `The SSH server is enabled.` appearing
on the screen.  Pressing the enter key, and then selecting `Finish`, I was then back at the
command prompt.

This was the moment I was working towards: being able to have a bare bones system to use that
I could access from my own computer.  Entering `sudo reboot`, I waited about 45 seconds for
the system to reboot and to be greeted with the `raspberrypi login:` prompt.  Looking just
above that text, I saw the text:

```text
[ OK ] Started OpenBSD Secure Shell server.
```

This gave me a bit of confidence to move forward.  At the very least, the operating system
was indicating that it should allow SSH access.  At the command line, I entered:

```text
ssh pi@192.168.2.3
```

and with the exception of the input `yes` to answer the question, the output was as follows:

```text
The authenticity of host '192.168.2.3 (192.168.2.3)' can't be established.
ECDSA key fingerprint is SHA256:`some text here`.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '192.168.2.3' (ECDSA) to the list of known hosts.
...
pi@raspberrypi:~ $
```

!!! note
    After each repeated installation on the same Raspberry Pi, when I went back to open a new SSH connection, it would report the error `WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!`.  To allow access, I needed to edit the `~/.ssh/known_hosts` file and remove the line for the IP address of the machine, as indicated at the end of the provided error message.

## What Was Accomplished

This article detailed the steps taken to install the Raspbian operating system on a MicroSD
card.  It started by my formatting of the MicroSD card and copying the NOOBs installer onto
the card, followed by inserting it into the Raspberry Pi's MicroSD slot.  The steps continued
with the largely automated installation of the operating system, only requiring the answers
to six questions on my part.  Finally, it concluded with the setup for SSH to allow me to
configure the Raspberry Pi remotely.

## What's Next?

In the next article in this series,
Glanceable Displays: Fine Tuning A Raspberry Pi Installation,
I walk through the steps I took to move the installation from a bare bones system, to one that
had Wi-Fi and time support set up properly.
