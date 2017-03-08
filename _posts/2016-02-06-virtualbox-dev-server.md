---
title: "Using an Arch VirtualBox as a Local Dev Server"
date: 2016-02-06
category: dev
---

My main machine at home is a Windows 7 box. It's great for gaming and other media consumption, but I can't stand the ecosystem for dev work. I'm more comfortable with the Unix side of things. So I've usually resorted to dual booting or using the Macbook. I go in spurts though, and if I go a few weeks without touching the Linux side of things I feel like I've let the OS down. Like an unmowed lawn. If I switch to a VirtualBox, I thought, maybe I'll hop back and forth between the two operating systems enough to maintain each of them properly.

I installed Arch using some default VBox settings and it worked great. I configured it to my liking: [unixporn][] style with bspwm and urxvt and nothing else. I figured I wouldn't have to worry about memory issues if I never installed a browser or anything like that. That was the whole idea behind the virtual machine.

Then I hit a roadblock.

I cloned a jekyll project to start working on it, but I didn't know how to serve it. I typed `jekyll serve` as usual, but instead of seeing a friendly LAN IP address, I see `127.0.0.1:4000`. I tried typing that in my browser on Windows without any hope and sure enough, no jekyll site.

So, how can I connect to my guest machine?

The answer was bridged mode, but it didn't work right away, or so I thought. First, make sure the host machine is using a static IP. Then, With the virtual machine powered off, open up it's settings and go to the Network tab. There should only be one adapter enabled. Attach it to the `Bridged Adapter` and make sure Promiscuous Mode in the Advanced section is set to `Allow All`. Save the settings and then start the virtual machine.

At the time of writing, Arch is using `netctl` to control [networking][]. Since this is a virtual machine, we can pretend that it is using a wired connection (just like my host machine, but I don't think that's important...). Arch comes with a few example `netctl` profiles located at `/etc/netctl/example`. Copy a profile and then begin editing, using the following code as an example. The interface can be found using `ip addr` and the gateway IP is the router's address.

    $ cp /etc/netctl/example/ethernet-static /etc/netctl/
    $ vim !$

    # example file
    #-------------
    Description="Basic static ethernet connection"
    Interface=enp0s3
    Connection=ethernet
    IP=static
    Address=('192.168.1.3/24')
    Gateway='192.168.1.1'
    DNS=('192.168.1.1')

    $ netctl enable ethernet-static
    $ netctl start ethernet-static

The last two commands start up the connection. You should be able to `ping` outside websites (e.g. google.com) as well as the router or other machines on the local network. Or at least I could. So I served the jekyll site on the Arch box and loaded up `192.168.1.3:4000` in a browser on Windows and I still got nothing!

I went on a wild goose chase looking for my problems:

- <del>trying to set up host-only adapters</del>
- <del>double-checking firewall rules</del>
- [reloading virtualbox kernel modules][archwiki-vbox]

That last one might is important, but I had already done it. The real issue was with Jekyll the whole time! Here is the magic command line flag that allows cross networking:

    jekyl serve -H 0.0.0.0

I don't know if the address is important or not, but I got it working so I'm not touching it. The yak is thoroughly shaved but I haven't gotten any work done on my Jekyll project. Hopefully this helps in the future though!


[unixporn]: http://reddit.com/r/unixporn
[networking]: https://wiki.archlinux.org/index.php/Netctl
[archwiki-vbox]: https://wiki.archlinux.org/index.php/VirtualBox
