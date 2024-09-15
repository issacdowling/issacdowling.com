---
title: "Transcript: Game Streaming on Linux (like Parsec)"
date: 2024-09-15T01:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
I've done a lot with remote desktop and game streaming on Windows, but on Linux, things
just must be different, right?
Like Wayland must make things super complicated, and even if it worked it would be a pain to
set up for users, and I mean Parsec doesn't even support Linux, so yeah we've got really
slow remote desktop like with VNC, but that's not what you're gonna be gaming with.
Except, actually, no.
It seems like the only reason Parsec doesn't support hosting on Linux is because, well,
it's for gaming and creative work, so it makes way more sense to focus on macOS and
Windows, but it seems like Parsec's prioritisation based on the kind of workloads they expect
people to be running is the only reason, since it's completely possible to have a Parsec-like
experience whether you're on Wayland or X11 on Linux with all of the software being
free and open source.
And as a bonus, if you're willing to go through a little bit more setup, and anywhere
from no extra hardware to a very cheap small amount of extra hardware, you can make it
so you can remotely wake your computer, so it doesn't need to be on all the time, but
you could still choose to stream from it any time.
That'll save you a bunch of power, which will obviously save you a bunch of money and be
better for the environment, and it's really easy so I suggest you get to that once we've
gone through the game streaming part.
The guide comes in a second, since why bother teaching you how to do something you haven't
even seen yet.
So there you go, same contents on both screens, that trackpad works and that mouse works.
Obviously the aspect ratio of the monitors don't line up, but you're not going to be
looking at both monitors at the same time, so you can just change the resolution, have
it look wonky on the host one but look correct for the device that you're streaming to, and
then it will all be fine.
If you've looked into remote desktop streaming before, you're probably aware of the software
that I'm using for this, but if not, on the host computer I'm running something called
Sunshine, and on the client, which by the way could be basically anything like an old
Android tablet, a Linux or Windows or Mac OS laptop, a smart TV, a PS Vita, a Wii U,
there are many clients, on those you'll be running Moonlight.
Sunshine connects to Moonlight, Moonlight shows what Sunshine is sending.
You're probably more likely to be familiar with a piece of software called Parsec.
It's called Parsec on both sides, so it's just the Parsec host and the Parsec client.
However, as you're also probably aware, that is only available to host from mainly Windows,
and I'm not sure if Mac OS hosting is out of beta, but I believe Mac OS at least somewhat works.
And the reason that Parsec was an innovation over things like TeamViewer and VNC is because
you're used to not really expect users to be doing anything demanding over a remote
desktop connection.
You might be remoting into a server if it has a graphical environment for some reason,
or going into a friend or family member's computer to help them change something because
they don't know how to do it, but besides that you're wanting to get in, do something
probably involving just editing text, and then leaving.
But what the Parsec team realised, and I'm saying the Parsec team, but honestly Nvidia
figured it out way earlier with in-home game streaming, and then Parsec made it more popular
with other people, and Sunshine and Moonlight actually re-implement the Nvidia protocol
except you can use it on any device, but meh-
Those people realised, wait, we've all got now dedicated video encoding hardware in our
computers that can encode high bitrate, full resolution video, really really quickly.
So why not use that, and the fact that, and I can sympathise if it's not happening near
you, but at least around me, internet is constantly getting cheaper and faster and more fibrey
for everyone around.
With all of that happening, why can't we have remote desktop that looks great and is super
fast, so we could use it for things like gaming?
Obviously it doesn't solve the issue that things like Project xCloud are trying to solve,
where you don't really need any hardware, your phone or whatever can just act like a
thin client, however it does solve me being far away and wanting to play games that are
harder to run while not being able to afford something portable that can run things that
well.
You know, travel light, game heavy.
And since you've all seen remote desktop stuff before, you know, game happens here, but game
seen there, wow.
I would like to test the latency stuff up front, since if that's awful, if there's something
wrong with the encoding, if it looks terrible, nothing else matters.
The test setup I've got for latency is just the UFO flicker test being recorded at 240
frames per second, and me counting the frames between something being shown on the original
display and something being shown on the remote display.
Obviously, the response time of the display matters there, so that's an issue with my
testing, and also recording at only 240 frames per second means if I'm rounding everything
to the nearest millisecond, which I have done, I've got a precision of about 4 milliseconds.
So if there was a 2 millisecond gap between things, someone with a 1000 frames per second
camera could see that, I couldn't.
But my test setup is accurate enough to at least be able to give you a vibe.
Is this good latency?
Is this bad latency?
I can tell you that.
So let's get to it.
We're gonna start with my best case scenario.
It's not the best case scenario, that would probably be two computers hardwired together
and they both have 480Hz monitors with 6GHz processors or whatever, but the best reasonable
real world scenario that I've got.
Which is my phone which has a 120Hz screen on a WiFi 5 network, so not some crazy unattainable
thing, it's coming from just an ISP router, connected to a computer on the same local
network and that computer is connected by Evernet to the router that the phone is connected
to.
And with that I get a very good and very consistent 29-33 milliseconds of latency.
I'm sure that if I'd left it going longer there would have been some random WiFi spike
that made it actually, you know, 29-33 99% of the time and 1% of the time is like a spike
to 100 or something.
But in actual gameplay, anecdotally that matches up with the data I'm getting here.
It's very consistent.
The latency is not just acceptable, it's better than a lot of TVs, wired TVs when they're
not in game mode.
If you're playing downstairs in the living room with people who aren't aware that you're
game streaming at all and your computer is upstairs, I'm confident that most casual people
would not know there is anything up with the latency.
It's excellent.
Like we think of the blink of an eye as pretty fast, but if soma technology is to be believed
this is three times faster.
Not that the blink of an eye is actually that fast in the context of display technology
but whatever, let's ignore that.
Let's get to remote testing.
Because I'm not going to, during this video right now, find someone who lives 50 miles
away whose house I can go to and film this and test that, I will say I have done this
at someone's house who is about 30 miles away and the results there were better than what
I'm going to show you because I'm going to be testing with 4G data.
So I've turned off 5G and the latency is quite significantly higher than me connecting to
someone with a fibre connection who's about 30 miles away.
So if you are connecting to someone who is a toll nearby, you know within probably 100
miles of you, the latency results that I'm going to show now are likely to be worse than
what you'll get.
You should have a better experience than these test results probably.
How bad or good are those test results?
58 to 75 milliseconds of photon to photon latency.
I mean that's noticeable, it probably will get you a few legit lag excuses when you lose
to someone in a game, but if it's that or nothing, that is a million times better.
It still feels pretty good, though you are starting to lose out on the ability to do
first person shooters or really anything kind of twitchy, but it's still pretty good.
Next I moved some testing over to my 60Hz laptop, which is more focused on creative
work and accurate colours than having a very responsive display.
So the response times are far worse than any modern LCD you're likely to experience.
This is a pretty worst case scenario for a machine that you're going to be receiving
it on.
And for that, on the same local network that my phone was connected to and that my computer
is on, I got 62 to 75 milliseconds of latency, which is pretty comparable to the phone on
data.
But that doesn't sound too crazy when you start considering, okay well, we add at least
8 milliseconds for the fact that we're going from 120Hz to 60Hz, and then you add the display
response times, you add the fact that it's just Linux, there's probably some more awkward
rendering things going on when it's not fullscreen, so on and so on.
It's not that crazy to see where the extra latency comes from, and again, if playing
on data on my phone was kind of reasonable, if imperfect, that same latency on the laptop
is still going to be fine.
We also see a similar jump in latency when comparing a connection on 4G, since there
we were getting, what was it, 95 to 108 milliseconds of photon to photon latency.
This is where you really start getting into, okay, I can definitely feel it, but it's still
in that close enough area where your brain doesn't get confused, you don't need to start
compensating for the latency too much if you're just playing simpler games, though it probably
will actually harm your performance for things that are even not that competitive.
So reiterating that subjectively, I'll say that yeah, on LAN with a high refresh rate
display, things feel practically perfect, to the point where I don't believe for anything
other than the snappiest of games that it's hampering me at all.
I suffered no stuttering, no blockiness, and very, very minimal latency.
If your home network is up to the task, and if it's not, I was just using Wi-Fi 5, you
can upgrade it to be as good as mine was in this demo very cheaply, you can have open
source in-home streaming that works practically flawlessly.
On 4G and for general remote connections, though, or if you have a 60Hz display or otherwise
a device that's adding more latency than that, like if you're streaming to a TV that
also has its own 30-60ms of latency to add, things are obviously less ideal, but like
I said before, you can still get by on it, and it's no worse than any of the other
streaming solutions that there are.
Plus, the issues that I did have with remote connections weren't huge.
There was the obvious constant factor of more latency, but the juddery or stutteriness
that was added was not very significant.
There were occasional, what felt like single frame stutters, but that was it.
There weren't big half a second pauses and it wasn't happening consistently every
few seconds, there was just a little bit of it.
Which is why, in my mind, comparing something like Sunshine to Parsec is very different
from comparing GIMP to Photoshop or Kdenlive to Resolve.
Because no, I'm not losing anything, anything at all by going with this open source option.
I understand that there are features other people might miss, like there's Parsec Arcade,
there's just no Sunshine alternative, or the fact that Parsec will automatically happen,
you know, opening a port for you so people can connect to you, Sunshine won't deal
with that.
Though I think there's a GitHub project that will do it, or maybe you, I'm pretty
sure you can actually enable UPnP, but it won't be as seamless, you will have to ask
it to do that.
But in my opinion, that's just good, that's just it being more configurable rather than
doing things automatically in the background, I actually prefer that.
Obviously for some people, the fact that Sunshine is different will be enough to make it not
quite the same enough, you know, the fact that you'll have to relearn a few minor things,
such as also actually not being able to divvy out permissions per client, to my knowledge.
So I can't say this one person can have just controller access, and this other person can
have mouse and keyboard access, but not controller.
When you set those kind of things up in Sunshine, you're setting it for all clients, not one
individual one.
And yes, that is actually a genuine loss, but I didn't use that myself.
But overall, I would say it's practically the same as the proprietary solutions for
most people, and it's the same for me.
I lost nothing, and I find that valuable.
Setup is super easy if you're on Windows, where you can just install it and run it and
you'll be fine.
But on Linux, it's actually mostly the same.
It does have a Flatpak, which is my preferred packaging format, so I would have loved to
use that, but I had some issues, I couldn't get encoding to work, and if I really think
about it, even though I do prefer Flatpaks, it's not like most Flatpaks have something
in the description where it's like, just modify these settings and change the ownership, and
then the Flatpak will work.
The whole point is kind of sandboxing and using portals and the proper Flatpak permission
system, so if I have to do that anyway to get the Flatpak to work, it's not much of
a loss just using the RPM, so that's what I did.
You can go on GitHub and just download the RPM or Deb or whatever you want for your
distro, maybe it's in your proper package manager in the first place anyway, not for
me on Fedora though, and then it will just work.
If you're on Fedora and you want hardware acceleration, you're going to need to remember
to download the special Mesa VA driver free world packages from RPM Fusion, since if you
remember a while ago they got rid of the hardware acceleration stuff for H.264 and H.265 a while
ago because of licensing things, which is really awkward, but you can make that work
also pretty easily.
And after that I needed to do no configuration, I just went to the web UI, set a username
and password, and was able to connect from Moonlight by just it showing me a pin, me
entering that pin on my computer in Sunshine, and it worked.
However at the very least, if you're going to configure something, on Sunshine's end
I would recommend enabling encryption on LAN, not because I expect most of your LANs to
be compromised and someone's sniffing all the packets and they could reconstruct some
sensitive data from it, but just because, why not enable it?
Encryption is super fast on modern machines, but it comes off by default for local connections,
so I think it's just better to turn it on.
On the Moonlight side, when connecting to Sunshine, I would recommend that you check
that you change your resolution, because I think for me by default it was only on 720p,
and up your bitrate to as high as your network permits.
It will give you warnings in the bottom right corner if you're having issues with that you've
set a higher bitrate than your network can handle, so you should never be having issues
about bitrate and you're just unaware, it should tell you.
You can also set in Moonlight whether you want it to capture system shortcuts, so like
I couldn't open my app menu with my Hyprland shortcut on the other computer unless I enabled
that, and there's a very useful setting to control whether you want the host computer
to be muted when you connect.
So if I was connecting because I was far away and I had my computer at home, yeah, I wouldn't
want sound coming out of the headphones even if no one's going to be at home to hear them
anyway.
However, if someone's connecting to me to do local split screen stuff, I still want
to be able to hear the game, so it's important to remember to turn that off.
Your audio isn't broken, you just need to change that setting.
If you're not seeing your computer appear in Moonlight at all, though you can still
change the settings before you click on the computer I think, that's the same as me for
whatever reason automatic network discovery doesn't work, but on your Windows computer
just go to the network settings, you'll find your IP, and if your remote computer runs
Linux just run ip a and check the IP address and you can just press plus in the top right
of Moonlight and add it there.
As I mentioned before, you can't currently set controller or keyboard and mouse support
per client connecting, but you can enable those things globally in Sunshine's settings,
not Moonlight's, which makes sense because you want the server to be setting those permissions,
so you can change those if you would, for example, like to do local multiplayer but
not want everyone who connects to be able to control your keyboard and mouse.
If you are planning on doing that, you'll also want to up the maximum number of connected
clients since I think by default it's just at one or some other very low number, you're
going to need to up that, or when someone connects it's going to kick off the last person
who was connected and you probably don't want that for a five person game night.
Another thing that Sunshine and Moonlight support is opening specific apps when you
start a connection, so the easy example and the one that they've got built in is Steam
Big Picture mode, when you connect, and it does that by just running any arbitrary command
that you can set, however, I've had two problems with that, firstly, there comes two desktop
options by default, there's desktop and low resolution desktop, except low resolution
desktop tries to set your resolution by using xrandr, that's not going to work if you're
on Wayland, so I just removed that option for me, if I want to change my resolution
I can change my Hyprland config, and the Steam Big Picture mode by default tries to
look at non-Flatpak Steam, it's easy to replace with Flatpak Steam, you can just change the
command, but that's probably important to know if you're thinking it'll try and do some
automatic detection magic and using Flatpak Steam, it won't, so remember to change that.
There are tons more configuration things that I've not covered here, but I think the last
super useful one that I need to make sure people know about is the fact that you can
change what client controllers will appear as, like if someone plugs a Playstation 3
controller into their computer and their computer has the drivers for it, it's not going to
show up to your PC as a Playstation 3 controller, it's going to show up as, I think, an Xbox
One, a Playstation 5, or I think a Switch Pro controller are the ones Sunshine can emulate,
so if you have a game that specifically only supports Playstation 5 controllers, you can
tell Sunshine, make every incoming controller show up as a Playstation 5 controller, or
an Xbox controller, and so on.
The two things remaining then are remote remote access, like not on your land, you know, outside
of the house, and being able to remotely turn on the computer.
For the former, I highly suggest just setting up a VPN on a Raspberry Pi, or if you have
a very fancy router, you can probably do it on that.
It's much more secure and more useful in the long term if you want to do other remotely
accessible things than just port forwarding, though you can technically just port forward
the ports that Sunshine needs.
If you want to be able to turn on your computer remotely though, well, if remotely just means
over the network, you actually don't need any extra hardware, you can get Android apps
for this, but if you mean remotely remotely outside the house, you are going to need at
least a little bit of extra hardware, like a Raspberry Pi.
And that's because the way we're going to do this isn't with a smart plug socket or
anything like that, it'll be with Wake-on-LAN, though I guess a smart plug socket could be
an option for you.
Basically, Wake-on-LAN works by leaving your computer's NIC, its Ethernet adapter, turned
on while the computer's asleep.
And when it's on, it's constantly listening for a magic packet, a little piece of data
sent over your network with the unique identifier of that Ethernet adapter, its MAC address,
contained inside it.
And that tells that network adapter, oh, I've just been asked to turn on, and because Wake-on-LAN
is enabled, I'm allowed to ask the whole computer to wake itself up.
And that means you could then do that from another app and move into Moonlight and now
your computer will be on and able to be accessed.
As I learned quite painfully though, magic packets and Wake-on-LAN work a bit more deeply
than the way I'm used to understanding networks, which is in the context of TCP IP.
You know, normally I think of, I have a computer with IP address X, you have a computer with
IP address Y, I know IP address Y, so I can talk to your computer.
But if your computer's asleep, it doesn't really have an IP address, so we can't really
do that.
And all the VPN, at least normally, is doing is giving your device access to your home's
local IP addresses when far away.
So yeah, you could try and talk to your computer's typical local IP, it's not going to be able
to do anything because it's asleep.
So I think that there are really awkward ways to make this work over a VPN, but the way
I'm handling this is having a Pi or a server or whatever locally, and that machine is running
some hardware where my phone can say, I would like you to Wake-on-LAN the regular computer
go, and then that sends a command to the server and from the proper actual local network,
it can talk properly and send that magic packet to the computer that's on the same LAN.
I feel like I have done a poor job of explaining it, so please correct me if you think you
know better in the comments because you probably do, but hopefully that's a good enough explanation,
even if it's not perfect, for why this normally doesn't work over a VPN.
You can get Docker containers that will handle giving you a nice web UI for sending that
Wake-on-LAN packet, or you can do what I did and find this Stack Overflow post where someone
does it completely in bash, that's what I use, it's kind of great.
Sadly though, Wake-on-LAN is even more mysterious than I've already told you about because enabling
it in the first place on the device that you want to target can be kind of awkward.
In my case, my motherboard has an option in the UEFI to enable Wake-on-LAN, so I enabled
it and it did nothing.
But then I found someone's magic incantations online for how to enable it within Linux,
which didn't really make sense to me because I thought Linux should be not active if the
computer's asleep, but after enabling it in Linux, it worked, and after then going back
and disabling it in my BIOS, it still worked, so Wake-on-LAN is kind of magic.
And now you should be able to use your Windows or ideally Linux computer for game streaming
without leaving it on all the time, and without compromising the nice experience that you
get from something like Parsec compared to the normal Linux VNC stuff that you might
be expecting.
Obviously, to actually do this you're gonna need to make sure Sunshine is actually running,
so you might want to make sure, if you want it to be accessible all the time, make it
so Sunshine starts on boot with the computer, but if you just want it to be accessible sometimes,
make sure to launch Sunshine before you sleep the computer and you go out if you plan on
game streaming.
This has been amazing for me personally, which is why I've wanted to make a video on it,
since firstly, now I do games design at college, and having a laptop that is as powerful as
my desktop would be prohibitively expensive, so it's nice being able to mostly use the
laptop that I do have, GTX 1060, but if I want to do something that's more hardware
accelerated in Blender, I want to run something that I couldn't, I can just stream from my
desktop, done, sleep it, I don't have to worry about power being always used, that's really
nice, and also just game streaming.
It's nice to be able to find an old split screen game that doesn't support multiplayer
and just go to my friends and be like, do you want to play this, yep, just join me.
It's really convenient and it's really nice now having this on Linux.
It's not like this is actually a super new thing to be on Linux, it's just I had always
had trouble getting it set up in the past and now it works for me so I wanted to share
that with you.
And just one final end of video extra mention, you might have seen a green line appear in
some of my footage on the side of the computer being streamed to, it seems like that's a
flaw of some hardware encoders and some clients when using H.265, you can fix that by switching
to H.264.
Plus if instead you want a cheaper but also less good Steam Deck alternative, you could
pair your phone with something like a Razer Kishi, £5 used so like, why not, and yeah
there'll be more latency but still you can get PC gaming stuff on the go and that sounds
really good.
I haven't actually tried it myself yet since I need to cut the bottom off this to make
it fit my phone because it's too big, but for £5 I'm willing to do that.
But I don't need to cut the bottom off: Russell Willis, Pieteek, pt1997, and Ducky! for them
to fit on my phone.
They're not actually on my screen but pretend I read them from my phone, see I didn't need
to do anything, those are my patrons and YouTube membership, subscribers, members, I really
appreciate them and you can join them through those platforms if you would like to.
So huge thanks to those people, join the Discord server if you'd like to be able to talk about
technology and see you next week, hopefully you've enjoyed.
