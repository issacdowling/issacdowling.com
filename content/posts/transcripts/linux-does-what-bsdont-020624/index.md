---
title: "Transcript: Linux does what BSDon't"
date: 2024-06-02T08:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
 Gaming on Linux, and using it as a desktop OS in general, is, I know, at this point,
 almost too good.
 But for real, even for complete newbies, as the Steam Deck has proven, it's actually
 getting more and more workable by the day, and for people more familiar with it, it can
 basically do everything you need.
 But wouldn't it be kind of nice to be able to relive the earlier Linux gaming days, with
 Steam running through wine and app compatibility being more hit and miss, but that leading
 to a tighter and smaller community?
 Maybe I was being a bit too harsh, but the fact that the various BSDs exist is nothing
 but good.
 It's just, I don't think anyone, even in their community, would pretend that they're
 ready as a desktop operating system, when even most Linux users tend to realise that
 our vastly more recognised OS is still not really ready for everyone.
 Despite that though, I do hear that there are a dedicated few who really do run it as
 their desktop OS where they do desktop things, and one of those includes gaming.
 Could I join them?
 Well, rather than wander any longer, I just went and put FreeBSD on a Ventoy USB stick,
 which lets you have multiple bootable images on one USB rather than having a dedicated
 one for each.
 The only problem is, that didn't boot, so I went and gave it its own USB stick, and
 that worked.
 I went through the installer, which is obviously not super fancy, but it's perfectly workable
 and absolutely no problems with it.
 It was actually very interesting to see that ZFS is an option for your boot disk, which
 is kinda cool, actually, and I was dropped into a terminal.
 I then was just about to follow the guide for how to install KDE and realised I had
 no internet connection.
 In fact, I had no interfaces to get an internet connection from.
 It seems like because my motherboard has 2.5 gig LAN rather than the typical 1 gig, maybe
 it's too fancy for FreeBSD to have had in by default, maybe it's too unusual, which
 is somewhat surprising given it's the cheapest B650 board I could find, but I don't know.
 The most obvious thing to do from there would probably actually have been to use a USB ethernet
 adapter, and I do have one of those, but it's on a USB hub.
 That wasn't my first thought, it was to use my phone and tether over USB, which did actually
 give me an interface but not an IP address, and it seems like that's because it's not
 getting a DHCP lease by default, so I had to run dhclient ue0, which then asked my phone
 for an IP address, and now it has one and internet connection works.
 From there I followed the KDE and AMD graphics driver install guides, which were very easy
 to follow, and shockingly simply, I was at a desktop.
 It just looked like Linux.
 There were a few weird things, like my monitor only being able to go up to 120Hz rather than
 144, not that that impacts the experience much, and that because I set no password for
 my user since I was just going through the installer quickly, I can log in through SDDM,
 like the default login screen, but if my computer locks, I have to fully log out and log back
 in, because the lock screen doesn't allow me to enter an empty password, it just says
 I'm wrong.
 But besides that, everything seemed normal.
 So I just installed Doas, which is like Sudo but simpler, which gave me permission to install
 packages with my normal user account, and used that to install Firefox so I could browse
 the web, and I used that to post about my achievement on the Fediverse, along with testing
 screen sharing on Discord, which surprisingly worked fine.
 Well the first thing I did so I could capture this better for you was install OBS, which
 is a ridiculously complex piece of software and so, as you might expect, it went terribly
 easily.
 I was incredibly impressed, to the point where I was just like, let's not even bother with
 anything more simple, OBS works, let's just go for Steam.
 So I downloaded WineProton from the official repos, installed the 32-bit extra things that
 you need, which involved it telling me I'm on the wrong version of the OS and me telling
 it to shush and ignoring that.
 I installed other prerequisites you're meant to need, installed Steam, that worked, went
 to launch it, and it gets stuck in an infinite loop of about to being able to log in, and
 closing, and being about to be able to log in again, and closing.
 I do get Steam working later, but for now, let's try non-Steam games, specifically Minecraft,
 because as it says in the name, Minecraft Java Edition is written in Java, and the kind
 of cool thing about Java programs is that they're not written and built for one specific
 OS, they're built for the Java Virtual Machine, or a Java runtime.
 And with that, you can then build one of those for an OS, and any Java app that should run
 on the runtime will run on whatever OS is running the runtime.
 And that should mean that Minecraft doesn't care whether it's on Mac OS, Windows, Linux,
 or FreeBSD.
 Despite that, obviously, the real world tends to be a bit messier, but the only way to actually
 find out for sure is to try.
 So I followed the OpenBSD build instructions for Prism Launcher, which is a third party
 Minecraft launcher, that worked fine.
 Java was already installed, I downloaded 1.20.6 along with sodium and iris, because I wanted
 better performance and I wanted to try shaders, and it didn't work.
 But only because I had Java 17 and 1.20.6 wants Java 21.
 After installing 21, it said I was on 21, and the game thought I was on 17 still.
 So I just downloaded 1.20.1, and it worked, but performance was terrible.
 Frame pacing was really bad, even if the FPS number, 90, was lower than you would want
 for Minecraft, but still, by itself it looks like it would have been reasonable.
 And when I tried to use shaders, well, they turned off my whole computer.
 However, after I restarted my computer from that huge crash, Minecraft performed fine.
 I was getting hundreds of FPS, and when I enabled shaders, those seemed to work fine
 too.
 I did get a few more crashes later with shaders turned on, but I ended up figuring that out
 while I figured out the rest of the Steam things, which again, come later.
 So if you play Minecraft, you can probably use FreeBSD just fine.
 It was really impressive that it was using my GPU, and it was just fine, nothing special.
 But although it's maybe less impressive that I'm running this inherently cross-platform
 app, Minecraft Java Edition, like I mentioned before, I've got two counters to that.
 The first being that everything but Minecraft is actually running native.
 As far as I can tell, KDE running natively, Firefox running natively.
 I think the graphics drivers are actually ported from Linux, but still running natively.
 So first, we're not actually using compatibility layers for that much stuff.
 But also the second thing is that, well, technology like that is just how lots of apps get shipped.
 Whether we like them or not, mainly Electron is the example people use that they don't
 like, Java isn't normally fine, whether you like it or not, lots of programs just are
 shipped in cross-platform ways.
 And although native apps are often nicer, we do kind of have to admit that it's the
 only reason a lot of apps work on Linux or FreeBSD.
 Case in point, another big thing I do on my computer is development, and unsurprisingly
 the main core tools of that, so Golang and Python, were native here, but VS Code isn't.
 Except it's not native on anything, because it's an Electron app.
 So I was able to find instructions for installing it on FreeBSD, and apparently you just need
 to run package install vs code, which didn't work, so fine, I'll compile it myself, except
 the computer crashed again while compiling things, which I still need to get to fixing.
 So while I was restarting that compile, I wanted to look into why couldn't I just install
 it when the guide said I could, especially when it seemed like it was coming from a website
 that should know a lot about FreeBSD.
 Well, it turns out that my actual issue was being on the quarterly release of FreeBSD,
 or the quarterly packages, when I wanted to be on the latest packages.
 After switching over, not only did I manage to install VS Code, but I got a bunch of wine
 updates, which might help Steam compatibility.
 And VS Code?
 It worked fine.
 My extensions, my theme, Golang and Python all worked completely fine, and I nearly forgot
 that I wasn't on Linux.
 I actually tried to run my self-hosted voice assistant program, which nearly worked, all
 of the code that I wrote worked, but the tooling for the machine learning bits doesn't seem
 to be there for FreeBSD yet, or I would have had to manually compile them or something
 like that, I didn't manage to get that working.
 But that's not the development environment's problem, that's a separate package problem.
 Obviously it's not exactly the same environment I'm used to, I normally use Hyprland rather
 than KDE, and I had a few audio glitches whenever I would turn on or off my computer and once
 while I was just randomly doing things, but in general it really does feel extremely familiar.
 Plus, while I was setting up all of this VS Code stuff, I managed to figure out the
 crashing issue.
 In the installer, it mentions something called PowerD, which should allow the processor to
 change its frequency rather than just being stuck at base, so that would be good on laptops
 to save power and good on desktops because it should let them boost, I think.
 However that seems like it was causing stability issues for me, and disabling PowerD seems
 to have fixed things.
 So things work now, and I can do what I normally would.
 On that note, I said we'd be back to Windows games, and here we are.
 So no more waiting, that is Steam running on FreeBSD, modern Steam with no graphical
 artifacting or anything, because it turns out I was going about things all wrong.
 Originally I was trying to run the Windows Steam client because, well, that's how we
 used to do things on Linux, and that's what a few guides for FreeBSD mentioned.
 However it seems that the more modern approach to things is actually running the Linux Steam
 client on FreeBSD because of FreeBSD's compatibility with Linux binaries.
 Then you use, you redirect Steam trying to use Proton to the version of Wine that is
 installed natively on FreeBSD.
 The problem with that, and the reason I didn't go with it the first time, is because multiple
 places were talking about how you need an Nvidia graphics card or graphics acceleration
 will not work.
 And it just overall sounds like a more complicated way of doing things, there's just a lot
 more steps to it, it feels like.
 And even the most official guide that I could find related to this mentioned that support
 for 3D accelerations on AMD graphics cards like I have was unknown, which wasn't super
 encouraging.
 They had a script, apparently, that should let you figure out whether it will work.
 I didn't bother with that, I just installed Steam and it worked.
 The entire steps going from start to finish, starting installing FreeBSD to having Steam
 working was that I installed FreeBSD, followed the install handbook for instructions on installing
 KDE and AMD graphics drivers, oh and nearly forgot like I mentioned before, changed the
 package repos from quarterly to latest, installed the Linux Steam utils package and followed
 all of the instructions it gave about changing some security options with the kernel, which
 I know, handwaving away security things always goes super well, ran steam install, which
 is a command that downloads the actual Steam installer from Valve, and ran Steam, which
 ran Steam.
 After that I had to make sure that I had followed the steps on the GitHub page about how you
 need to make sure that Steam can actually redirect to your FreeBSD install of Wine.
 And then the first two games I tried worked fine, that was Superhot and Stick Fight The
 Game.
 The first time I launched those, performance was terrible.
 We were talking in Stick Fight The Game, I was getting like below 30 FPS on an RX 6800,
 that makes no sense.
 And in Superhot, again, I was around 20 frames per second.
 That sounds like maybe it could be shader compilation or something, but that is way
 worse than shader compilation would be.
 Whatever reason I was getting that bad performance for though, it went away upon the second launch
 of every game, and Superhot, perfectly playable, Stick Fight The Game, perfectly playable,
 and I checked online works there as well.
 I did then enter an unlucky streak where the next three games I tried didn't work, Splitgate,
 which is a native Linux game, gave me a Vulkan driver error, No Man's Sky just said hello
 games and then shut down, and Chaos, which is a Windows game, just didn't work.
 Obviously it would be nice if it was just as compatible as Wine or Proton on Linux,
 but games is games, and it seems as with Wine on Linux, the less complicated the game is,
 the more likely it is to work.
 One mistruth I see pretty often, or at least one out of date fact that I see pretty often
 with Linux and the fact that I use it to make videos, is that DaVinci Resolve can be really
 hard to set up, especially if you have an AMD graphics card.
 And that's just not the case, at least if you know to use a distro box to simplify
 all of that.
 But it seems like on FreeBSD I am actually out of luck as an AMD user.
 It seems like someone actually has gotten Resolve working, the Linux version of Resolve,
 which is really impressive, but using NVIDIA CUDA rather than AMD ROCm, which doesn't
 seem like it's an option here, which is a shame since I would have really liked to try
 that out.
 However, Linux users were putting up with this level of software compatibility, both
 like productivity software and games, just a few years ago.
 And so I think if you're a Linux user who really is trendy enough to see Linux getting
 more popular as a bad thing and you want to switch away from it, honestly, FreeBSD isn't
 that bad.
 And if you just like FreeBSD, I'm just super shocked to see how well it all mostly works.
 I really was coming into this expecting 99% of things to be in the terminal, GUI apps
 that all look like they belong in XFCE, just general bad performance, a lack of 3D acceleration,
 and just trouble at every possible turn.
 And that really does seem like an exaggeration of how I was feeling now that I've really
 experienced it.
 I'm super shocked at how similar the experience of using FreeBSD was to Linux.
 The only problem with that is when we get to motivation for switching.
 Obviously I'm not going to be switching to FreeBSD, but let's pretend that compatibility
 was the same.
 Why not, if that were the case?
 And the main reason is when you're coming from Windows to Linux, you get this big, huge
 experiential shift.
 You go from proprietary to open, bloated and awkward, to modular and lightweight and customizable.
 But going from Linux to BSD, we're both on the same team, which is nice because generally
 the software seems to be pretty similar, you know, KDE on both.
 However, that also means there's not too much of a difference.
 There's the Linux way of doing things and the BSD way of doing things, but they both
 fall under the same category of, well, probably cooler than how Windows does it and open source.
 And kind of because of that, I was allowed to come in and basically just have a Linux
 desktop experience, but worse.
 I wasn't taking advantage of any special FreeBSD things, just like the kind of Windows users
 that Linux users complain about, where they come in with a Windows mindset, do things
 wrong and go, ah, why does this operating system not work for me?
 That's kind of how I came in, except it actually mostly kind of did work for me.
 So I think as I do obviously move back to Linux, I'll still be able to appreciate how
 surprisingly decent it is for the other member of the free operating system team.
 And if you want to join the team of people who I thank at the end of videos, that's Ducky!
 and pt1997, you can join on Patreon or YouTube memberships if you'd like to.
 So huge thank you.
 Hopefully you've enjoyed, subscribe if you'd like to, and bye, I'll see you next week.
