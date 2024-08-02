---
title: "Transcript: Turning a Switch into a Steam Deck / Linux Mini PC"
date: 2024-08-02T01:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
The Steam Deck is large, heavy, and expensive, maybe not in the context of other PC handhelds,
but definitely when compared to a Switch.
And regular PCs tend not to be particularly mini or ARM-based.
Yet we've got native Linux programs running on the Switch.
Before we get into trying different software, where obviously there will be gaming, I just
want to start with the fact that this really works.
And to reiterate, this is not game streaming.
This is running natively ARM stuff on the Switch.
The GPU, CPU, the display, Wi-Fi, audio, all of it just works on the Switch, Joy-Cons too.
It's really impressive, and not even that difficult.
It's not like it's secret information or anything, but I won't be sharing exactly how I did it
in this video to keep Nintendo from getting too annoyed.
All I'll say is I put the Switch, my phone, a USB-C to C cable, and a staple in a box,
shook them around, and they came out able to do some really cool stuff.
I had the choice of a few different versions of Ubuntu or Fedora 39 to put onto the Switch.
And I ended up going with Fedora 39 since it's just more familiar to me, like I use
Fedora on my own things.
And also, I wasn't aware at the time that Ubuntu has a few extra little scripts and
goodies to make things easier on the Switch, but we'll see how Fedora goes.
The desktop that it drops you to is KDE running X11, and I tried Hyprland since I really
wanted to use it, but it crashed on launch, so I wonder if there's an issue with Wayland
potentially?
The only modifications to KDE, or not really modifications, but the only things out of
the ordinary on your desktop are some desktop icons for some NVIDIA tools, because there
is an NVIDIA GPU in the Switch, even if it's an old one, a shortcut to the GNOME terminal
from KDE, and an icon that looks like it's a folder, but says it's a readme, but actually
is a .desktop file, a shortcut to an app that doesn't seem to be installed.
On the bottom right, you've got a little touchscreen icon to say, open the onscreen keyboard, but
you can also use the plus button on the right Joy-Con to do that, a button that lets you
set a charge limit or see the Joy-Con mappings, and one that lets you overclock really easily,
you don't have to enter anything specific, there's just six different modes along with
being able to set the fan profiles, or let it do that automatically.
And the final thing isn't actually a special addition, since they probably actually just
do it over Bluetooth and they haven't done anything special, I'm not actually sure, but
it's kind of nice that the Joy-Con batteries show up as battery percentages in the battery
icon, or under the battery icon.
The only other weird thing I noticed about this install is that they went with Chrome
rather than Firefox, and they have Chrome and then like a game streaming with Chrome
shortcut in your app menu, but both of them seem to just open Chrome.
Very shockingly, sleep works great.
It is on the official feature list, I just missed it somehow, but it really works.
Overnight in sleep mode, it only lasts like 6 or 7%, and I was just expecting either sleep
to not be implemented, or it to wake up super hot or something, but I guess it isn't a Windows
laptop, so why would I expect that?
The actual reason I tested sleep, despite expecting it to fail, was because I didn't
want to leave it on charge overnight, since then it actually would get hot, but I also
didn't want to turn it off and turn it back on again, since it's really awkward to get
back into it.
I won't go into the exact details, keep Nintendo happy, but there's a reason I mentioned a
staple, it would have been pretty awkward if I had to reboot Linux all the time, but
I ended up being forced to, since after sleeping and waking enough times, wifi stopped working,
so I went and rebooted anyway, and was pleasantly surprised that rebooting Linux literally restarts
just Linux, but the whole switch system stays on, so you don't end up needing to remod things.
Once I figured that out, I finally installed all the updates, since even though you can
install things on Linux and you don't need to reboot, you probably should reboot for
things like kernel updates, so that kinda pushed me to updating, but yeah, I was very
shockingly impressed that things were so smooth.
Sadly, I didn't end up being able to upgrade all the way to Fedora 40, it was just the
most up-to-date version of Fedora 39, because when I tried a major version upgrade, it warned
me that some switch-related packages were going to be uninstalled, and I didn't want
to do that, so it seems like we are going to have to wait for Fedora 40 to be officially
supported before doing that, but still, it's mostly up-to-date.
The only real thing I've got left to tell you before we start trying some stuff is that
OBS works.
This was something that I thought of in the FreeBSD video as well.
I keep expecting OBS to fail because it's such a big and complicated piece of software.
If it works on a switch, on an ARM CPU that's like really old, I think I'm going to stop
expecting OBS to break.
This is really impressive.
Alright then, now the tour's over, let's get to gaming, where we'll also be trying regular
software since this is just Linux too, but we'll start with the gaming, where first
we'll start with the extra most awesome games, open-source ones, specifically because that
means I can try them natively and without WINE to get an idea of what the switch is
capable of before we add any layers in between the game and the switch.
So does it at least minimally work?
Yes, actually, resoundingly.
Not only did the Joy-Cons just work in SuperTuxKart immediately with no effort, SuperTuxKart
also ran fine, Vibration worked, which I didn't even know SuperTuxKart had, and although
I had an issue at first where some of the bindings between the game and some like Switch
mod Linux bindings that let you control the desktop easier were conflicting, I found out
the little screenshot button lets you disable those and then the game gets exclusive access
and it works perfectly.
Like, I know the switch is known for a different racing game, but I know which I'd rather have.
I next tried Xonotic, but that didn't get through the menu, which is kind of a shame,
and I wanted to try Hurry Curry since I saw that was a new game that looked kind of like
Overcooked and it was on Flathub, however that just didn't launch.
So I thought, well, the only logical next step to take is Minecraft Java Edition, since
the Switch is normally stuck with Minecraft Worst Edition, Bedrock Edition, so it'd be
cool if there was a way to play that on the Switch.
And I downloaded Prism Launcher from Flathub, but it just didn't launch, and I looked into
the error and I managed to find a fix online by setting this environment variable to no.
However, even once I stopped Prism Launcher from complaining, Minecraft still didn't find
a GPU, so I was unable to try it.
Are we just out of luck?
Ignore what you can see there.
Hopefully not.
My hope is that if I try following the steps to install x86 Steam, maybe x86 Minecraft
Java Edition will work and it's just some weird arm thing.
So I did it, it involved a Debian charoot, like it was kind of an awkward installation
procedure, but after trying it, Steam's little updater popped up and it never opened again.
This is just like what happened on FreeBSD.
I spent actual hours trying to figure things out until I remembered Ubuntu exists.
Ubuntu has all the easy things.
Let's try Ubuntu.
And Ubuntu is why - or, community-made help for Ubuntu is why - this is Steam big picture
mode running live on the Switch, and that's really cool.
Actually, I just want to double-prove that to you.
If I press the home button, it goes to the Ubuntu desktop.
That's not just a website running on the Switch or whatever.
I started my game testing with Superhot, which took like seven minutes to load, and once
I actually got to the start, I saw like a single frame of things being ready, and then
the whole Switch turned off.
I then tried again and it loaded way faster, and it turned off again.
So I'm kind of feeling like this was actually the maximum overclock that I set being unstable.
I do have the maximum overclock and fan speed maxed out, so I would get the best performance,
but I'll budge it down to the medium overclock, and Superhot actually ran.
I tried using MangoHud to get as good framerate stats, but that just didn't end up working
and I have no idea why, but Steam still has its old-fashioned FPS counter that's not
based on MangoHud, that's just a little number in the top left, and with that we can
see Superhot was getting anywhere from the mid-10s to mid-20s FPS, and with very, very
poor frame pacing, you would not want to play Superhot on this.
Stick Fight The Game did not launch, but now willing to try Minecraft Java Edition again,
still the ARM version, it actually worked perfectly, and with the normal performance
mods and controller support mods that I would play Minecraft with usually, it was actually
getting a bit above 50 FPS in normal gameplay.
If you want to try Minecraft Better Edition on a Switch, you can do it and it will run
perfectly well.
It did drop to just above 30 frames per second while generating new chunks, so as a Switch
player you could either make the choice to cap it at 30 and always be good, or cap it
at 60 and most of the time it will be at 60, but when you venture to new areas it will
drop a bit.
It's also worth noting that the GPU usage is very low, which is kind of a shame since
it points to this being a CPU issue, and I do have CPU performance mods on that should
be making that better, but it also means you should be able to have a decent time if you
were to dock the Switch in 1080p or even 1440p, maybe even 4K, running Minecraft because
the GPU is barely being stressed out at all.
The GPU is not why we're stuck at 60 or 30 FPS.
I tried Portal 2 (too).
I tried Portal 1 as well, not Portal 2, and it seemed to run, the FPS count had just disappeared,
it felt like it was running around 30 frames per second, but very consistently.
It was actually pretty enjoyable until the first Portal appeared, and then it dropped
much below that and there were big, maybe shader compilation pauses, I don't know,
there were just sometimes big pauses.
However, it does technically work.
But the fact that it can run Minecraft Java Edition better than it can run Portal tells
me that something is going wrong with the GPU utilisation when we're running x86 programs.
I do hear that Box86 and GPU acceleration doesn't work, but then 64-bit games, like
I think Superhot would be 64-bit, but then that seems like maybe it wasn't using the
GPU as well if it was running so poorly but Minecraft was running so decently, so I'm
not sure what that's about, but at least native apps seem to be doing fine, since Minecraft
and SuperTuxKart and therefore presumably emulators too even though I didn't try them would also
be fine.
To prove that, I went and tried Hurry Curry again, and this time it did launch, but it
seems like something on the main menu wasn't rendering because I couldn't get past it.
And yeah, I could spend more time trying to get other games working or emulation or anything
like that, but emulation would make Nintendo even more angry than they already are.
And well, as for other games, Linux users don't really play things on their computers,
do they?
Like, yeah I have a big GPU, but the most complex game I really play is Quadrapassel,
and all of my fancy configs and powerful hardware are for the hypothetical situation where I
might want to play games.
Kidding aside though, let's see how the Switch works as a little ARM-based mini PC.
That Ubuntu desktop you see behind you, that's why it's docked.
So ultrawide display output, check, it actually supports up to 4K30 on a regular 16x9 display.
Keyboard and mouse, all good.
And Firefox is fast enough, though somewhat disappointingly, and maybe this is something
I could have solved and made Firefox use hardware acceleration, but it seems like Firefox
might not be hardware accelerated and Chrome is, because where Firefox can't even play
a YouTube video smoothly, Chrome can nearly do 4K and can absolutely perfectly play back
1440p videos, along with generally feeling smoother, so, womp womp.
VSCode, since for this whole video we have kind of been on the path of me trying the
same things as the FreeBSD video, so may as well continue, VSCode does actually launch,
does actually seem to work, though I would be wary about using too many Electron apps
on a "computer" that only has 4GB of RAM, I actually saw so many low on memory errors
that I noticed there's a misspelling in one of them, I don't know if that's been fixed
in the newest versions of Ubuntu, but that's kind of funny.
But yeah, if I wanted to evaluate the desktop experience of it, I'd say, well, it's about
fast enough that anything you could do on a Chromebook you could do on here, though
if you really wanted a full Chromebook experience, you can just install Android on it.
There is basically no fan noise, though you can up it if you want lower temperatures,
but even then it's pretty quiet, and it mostly just works.
Graphics acceleration is obviously the most awkward part, but for anyone whose workflow
pretty much entirely consists of open source programs, Flatpak and Apt, or DNF, are just
going to download you the ARM version of things, which seem to be available for most packages,
and stuff is just going to run and load and you'll have no idea you're on a completely
different CPU architecture.
Plus, as we found out with Steam, you can emulate... emulate? translate... things? I'm not
sure what the right terminology would be, you can run x86 things mostly alright, though
obviously you shouldn't be expecting the same level of performance.
So yeah, the Switch is not a productivity or gaming beast, and I understand that I didn't
take full advantage of it and I probably could have done much more with it, but hopefully
you understand that it's probably not super practical for you to use this as a Linux desktop,
but I got as far as being able to prove that yes, it does work, and this was actually one
of the more fun little technology adventures that I've been on recently, because it's
relatively accessible, there were a lot of little awkward moments, but if you know a
way around Linux, you could probably have done this too.
Maybe it could even get you by if you don't have your laptop at some point and you need
to give a presentation and someone has a USB-C dock nearby, that's a valid point actually,
it does support non-Switch USB docks, I just used a regular USB-C hub for my testing of
docking it to my monitor, USB ports, HDMI, all worked perfectly.
So I give you the Steam Deck Lite, or Steam Deck 0.5, 0.25, 0.1, it's not really a Steam
Deck, but it's cool anyway, just like my supporters, I need to give a huge thanks to
Russell Willis, Pieteek, pt1997, and Ducky!, I really appreciate it, hopefully you found
this an interesting video, you can join them on Patreon if you'd like to, subscribe if
you'd also like to, and I'll see you next week.
I can't wave.
