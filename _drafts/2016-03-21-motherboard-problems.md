---
layout: post
title:  "Motherboard Problems"
date:   2016-03-21 10:26:00 -0500
categories: dev
---
The other day, I turned on my PC and was greeted by a warning saying my copy of Windows 7 was not genuine. I was a little miffed. TODO: add root cause here

Context: I built this machine myself. I honestly don't remember if this copy of the OS was genuine or not. I was fairly positive that it was, but there is a chance it wasn't. Either way, I've been using this machine without problem for at least a year. Something had to be wrong for it to wake up broken.

My first thought placed blame on Microsoft trying to get me to update to Windows 10, maliciously or not. I had deleted the notorious updates that caused the spontaneous upgrade, but I hadn't kept up with the news. I thought that maybe I wasn't thorough enough, the upgrade may have tried to continue without my knowledge, but because of whatever actions I already took to prevent this very thing, it may have broken halfway through.

Then I realized how paranoid I sounded.

After thinking more clearly on it, I settled on another possibility. A few days before, I had opened the case to show my brother-in-law the guts of my machine in order to help him out planning his own build. Being winter still, I wondered if I shocked something. Or maybe a connection was loose somewhere.

I opened it up, double checked connections, and did a quick visual inspection to see if any component may have been damaged. I didn't find anything, but the possibility stayed in the back of my head.

Next I dug into the software side of things. Using [this script][how-to-geek-1] I found my product key. I tried revalidating it, but it failed. So I gave Microsoft a call. Luckily I had an hour or three to spare. At the end of the many calls and transfers, I found out that my key was an OEM key not a retail key, so there was nothing they could do for me. They pointed me in the direction of the original manufacture.

So I'm again at a loss. I'm trying to remember how I bought my key, or if I pirated it. The only place that this key could come from was Asus. I have an EEE pc from them that came with Windows 7 Starter. I know I paid for an upgrade because Starter was practically useless. But I remember being on the phone with them trying to get a key because things weren't working. This is the only way I would have gotten an OEM key.

This key wouldn't be genuine in my new machine, but I didn't know that yet. After a few days of searching, I figured it out. I still have no idea how I got it to be genuine in the first place, or if I'm even on the right track. But these are the only pieces of the puzzle that remotely fit together.

Skip ahead a week or two and I'm troubleshooting the same machine, this time running a fresh, newly purchased version of Windows 10. The buggers strong armed me into shelling out a hundred bucks for a new key. But I have a new problem now. No matter what I do, my computer will not stay asleep. I followed [this article][how-to-geek-2] to a tee, nothing can wake my machine except the power button. But it doesn't sleep for more than 5 minutes without popping back on.

I looked at the logs and see this:

My system clock is all screwy. I remembered another oddity when I installed Windows 10: my time and date settings were wrong. I don't remember what I did to fix it, but I remember thinking that what I did was a hacky way of doing it. I just chalked it up to a buggy new OS.

I need to investigate more later...

[how-to-geek-1]:
[how-to-geek-2]:
