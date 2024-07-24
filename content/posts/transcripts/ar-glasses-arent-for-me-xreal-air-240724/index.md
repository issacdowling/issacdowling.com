---
title: "Transcript: AR Glasses Aren't For Me (Xreal Air / Linux)"
date: 2024-07-24T01:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Trancript"]
draft: false
showTableOfContents: false
---
 These are AR glasses. They've got Micro OLED displays above my eyes being reflected and
 overlaid onto the real world. They're extremely cool, surprisingly well built, and I spent
 a lot of time and even software development effort trying to fit these into my workflow,
 but they're just not for me. We're going to start by learning about the glasses themselves,
 and then we'll get to my experience with them. You can check the chapters below.
 My expectation when I ordered these was mainly to use them at college actually, or any other
 situation where I would want to use my laptop not at home. Since I thought, well maybe I'd
 be able to get multiple displays or at least one bigger display while I'm out, that could
 also save some battery life on my laptop because I could have its screen be off and
 I guess that would be a bit more private too. And yeah, just a bit to feel cool. And when
 they arrived, I really did think that they would be the future. The displays, the quality,
 they are just, they feel exceptional. This is my first time seeing Micro OLED in a product,
 and it's hard to describe what nicer colours feels like, but my background is purple, and
 it felt like I was seeing that background not with an inaccurate purple or a wrong purple,
 but just a different one, a new one, a deeper one. And that's probably the least precise,
 but most real way that I can try and express it. And obviously that doesn't mean they can't
 be improved, it would be nicer for them to be 1440p or even 4K, but 1080p is surprisingly
 good here, and I imagine that's due to a lack of a screen door effect, like there are no
 gaps between the pixels, so 1080p is just less of an issue here. Especially when it's
 running at 120Hz, which they do on the latest firmware when plugged into a computer or your
 phone if it's just display mirroring, but not when connected to the official app, which
 we'll talk about later. And I guess while we're on the topic, we should probably also
 talk about FOV, since even though it's not directly related to the displays, it's more
 optics around them, it's pretty similar, so we should just get to it. And my judgement
 is that it's fine. It's big enough that looking right into the edges of your virtual monitor
 is a little bit uncomfortable, so it's perfectly good for one static big display, but really
 not too much more than that, since actually as far as how much of my vision is taken up
 by it, it's not really any more than just being close to my monitor on my desk. But
 if you actually think about it, how much more of your vision is taken up by a cinema screen
 compared to holding your phone close to you? It is more comfortable in these, it feels
 like a big display that's far away, not a close-up display that's small. Even though
 if you actually think about it, it's a super tiny display that's super close. The built-in
 speakers and microphones are actually pretty decent. I mean, they're not the best, and
 the above-ear speakers are, as all above-ear speakers are, which is to say, not super bassy,
 but they get loud enough, and they won't distract people around you if you're listening
 at a reasonable volume, and they're not right up next to your ear. For the time that I did
 use these at college, I was happily listening to music through them, rather than my earphones,
 even if they did sound worse, it was just more convenient, and people around me were
 happily existing, none the wiser. Until they looked at me. Because it's not the fault of
 the bulk, it's not really even the fault of the design. No one at first glance noticed
 these little lumps on the top of the glasses where the displays are kept, and most people
 somehow actually didn't even see the two-lens thing that's going on. It's the fact that
 when you have these on, you can see a glowing rectangle of shapes and colours, which is
 actually just the other person seeing a tiny version of the screen that you're looking
 at. I'll actually take a sec to put them on so you can better see what I'm getting at.
 You can see, probably if I get up close, exactly what I can see, which right now is a video
 feed of me. And that is furthered by the fact that it looks like I'm wearing sunglasses
 indoors, so I'm inviting a bit of scrutiny when people go, what's going on? Wait, what's
 going on in his eyes? Wait, why are there two lenses? Wait, what's the deal with the
 lumps? So if someone's only looking at you for a split second, and your brightness is
 down, I'll turn it down, it should be less noticeable for you now, you might get away
 with it, but it's not like you could be wearing these and just nobody knows that anything's
 going on. Which, if these had cameras on, I would want people to know about them, but
 if it's just displays, the deal was kinda supposed to be that these are at least somewhat
 discreet and they're not particularly. But yeah, I hadn't even considered that if you
 don't have long hair, you've got no chance of being particularly discreet because you
 have a cable running down the left side of your neck. Let's focus for a second on that
 cable I mentioned. It's USB-C, which is really nice to see, and detachable from the glasses,
 so you should be able to replace it with other cables as long as it's not a really low quality
 cable that's missing some of the pins, it does need to be a proper good cable. However,
 as I somewhat alluded to earlier, you probably won't be able to get away with just any USB-C
 cable because it's angled coming out of the glasses, so you'll look especially weird if
 you don't have long hair and you just have a straight USB cable sticking out of the side
 of your head. The main interesting part about this cable though is what goes down it. When
 you think of video going over USB, you might think of what goes on with the Oculus Quest,
 where the Quest has a processor, the computer has a processor, and to get video from the
 computer to the Quest, it takes the raw frames, encodes them, compresses them, sends them
 over just regular USB data, and the Quest has the processing power to decompress, decode,
 show them. However, these glasses don't have the power profile or the space for a processor,
 so they don't do that. They use DisplayPort alt mode, which, if you're unfamiliar with
 DisplayPort, it's basically just HDMI but nicer. Basically, instead of spending a bunch
 of processor time encoding things into some weird format and getting them back and losing
 quality in that process, this just sends full raw video over the pins of a USB-C cable,
 which is great and it's a standard that's not a special Xreal thing, it's just that
 your desktop computer probably doesn't support it, though some do, your laptop maybe will,
 and your phone maybe will. Manufacturers aren't very forthcoming about the exact capabilities
 of their USB ports, and some parts, like DisplayPort alt mode, are optional. So, for example, it
 works on my laptop, it doesn't work on someone else's laptop I've tried plugging them into.
 It works on my phone, it won't work on most Pixels, except newer ones now support it.
 It's really awkward using this, but it's also kind of necessary for the form factor, and
 has the benefits of, well, it's raw video, unlike a Quest or anything else where there's
 video compression, where there's blocking and artifacting and latency, there's basically
 no overhead, basically no latency, and the video feed, as I said before when evaluating
 the displays, looks great. Just before you consider buying these, if you end up thinking
 about it after this video, remember to check online if people are having success with the
 configuration you're planning on using, or make sure wherever you're buying them from
 has a good returns policy. But for now, let's not worry about whether it works. If it does
 work, because it does for me, how well does it work? What can you actually do? Well, if
 you have a Mac or Windows PC, there's a piece of software called Nebula which lets you place
 a virtual monitor, rather than being attached to your face and following where you look,
 you can place it in the real world relative to where you look, and if you look away, it
 will go away. It's kind of, it's a bit more natural. It's kind of a flawed concept in
 my mind, because it.s. much more natural that way, but it also further shrinks the amount
 of display you can really have, because the FOV is already kind of small, but just,
 about enough, but now, unless you keep your, head perfectly still, you're going to have
 to, allow a little bit of extra room, so that when you move your head around, you're not
 cutting off parts of the display. But, that aside, that's a, pretty useful piece of software,
 and one I will try to clone, for Linux, which we'll get to later. But they also have Nebula
 for Android, which isn't quite the same, it doesn't offer you head tracks to display things, but, you
 can still mirror the display just fine. And, there's the Xreal AR space, which is an AR
 environment, it's 3D, it actually looks pretty good, it's kind of nice, you can still see
 the real world through the edges, and you actually control it, kind of like using a
 Wii remote, use your phone's gyroscope, and it's like the touchscreen as a trackpad, which
 isn't the worst method of navigation, given they don't have eye tracking. However, the
 movement drifts a lot, it's notvery consistent, you have to think about where you're pointing
 your phone to use things, and it's just not very intuitive, I've found. But also, there's
 just not a, lot to do in it. Like, if I were to be wearing these glasses 24-7, I can see
 viewing pictures in them being kind of useful. But I'm never, ever, going, to, without these
 glasses on, because I, you know, in the end I found it kind of socially unacceptable,
 and just kind of awkward still, even if I'm alone to have them on all the time, I'm never
 going to not have those on, and think, oh I want to view a picture, I'm gonna put
 those on, wait for AR space to load, and use their kind of awkward image viewer to view
 an image. I'm never gonna do that. Yet, the Nebula for Android app needs constant access
 to your images, even if you don't want it. They won't let you go into the AR space without
 that permission.
 Another thing that contributes to me not finding the AR space very useful, is that the web
 browser is very slow. Navigating to websites is kind of fine, and I don't have the newest
 phone, but it is from 2021, it's got a Snapdragon 888 in it. If I go to try and watch a YouTube
 video, and they have recommended YouTube videos on the front of AR space, it's too laggy to
 watch. It cannot do any resolution I tried at 30 frames per second. Beyond the AR space,
 the app also lets you take the regular, stuck to your face screen mirroring that you can
 get without the app, and the app lets you move that to the side a bit. Which sounds
 like a really good idea. Feels like that should be like when you get a video call in Cyberpunk.
 You could just have someone in the corner of your eye, or something in the corner of
 your eye. Sounds great. But again, the FOV means it's not really in the corner of your
 vision, it's just the center of your vision, but a bit off. It's still very distracting,
 and would still very much get in your way. And the final reason I would never use these
 connected to my phone is that phones aren't 16:9 anymore, but the displays in the glasses
 are. So unless you use something like Samsung Dex, which in fairness you can do and I've
 tried and that works, unless your phone has something like that, it's just going to be
 mirroring the phone display in the exact same aspect ratio. Which means you're not going
 to have black bars, because black for these displays means transparent, but you're going
 to have your image shrunken by the fact that this 18:9 image has to be squished onto a
 16:9 display. Which gives you transparent bars at the edges of your content, which is
 noticeable because it makes it smaller. Not a reason that I'd avoid this app, but also
 just another little awkward bit, is the Nebula for Android app needs Google services, and
 I have at least the basic Google services still on my phone, but the version from the
 Playstore doesn't work since I don't have Google services, and Nebula or Xreal has a
 Google Drive link on their support forums from which you can download a de-Googled version
 of the app, which is a kind of interesting way of doing things and I'm happy that that
 solution exists, I'm happy I could use the app as opposed to not using it, I just don't
 really get what the point is. Fine, you don't find them very useful when connected to a
 phone. But what about when they're plugged into a laptop, which was the whole main initial
 point? Well, I can't complain too much that Xreal doesn't have Linux support because I
 understand it's a smaller market, I have no idea if Xreal is a relatively new company,
 but these AR glasses are the first products I'm hearing from them, so maybe they're at
 least a relatively small company. I can see why Linux wouldn't be a focus, but I do wish
 there was at least an official Linux SDK even if there was no official Nebula for Linux,
 something along those lines, but we'll get to how that integrates with what I end up
 making later. Because the first thing that I was planning on using to try and get virtual
 desktops with those on Linux, actually does use the community drivers as a base, but is
 something called Breezy Desktop. It has changed quite a lot since I initially looked at all
 of this in April because originally it was pretty much Steam Deck only, technically you
 could use it on desktop Linux too, but it's main capability was getting one Vulkan app
 and putting that in front of you doing virtual desktop head tracking things, not really a
 whole desktop, just one program, ideally a game. However, since then changes have been
 made and the developer clearly has been working on getting GNOME virtual desktops, and that's
 great, this seems like it could be good software. However, I'm not super interested in it.
 Especially because I just don't use GNOME and I wouldn't have much use for just showing
 a single program, I don't plan on gaming in them much. But secondly, I won't exaggerate,
 it's not like it's super super bad, I completely get that the developer is trying to make money
 off it and is doing it by making great software. However, there is DRM, Google Analytics, and
 it runs as root. So I'm not super comfortable having it run on my machine, especially after
 that whatever it does caused connectivity issues between my glasses and my laptop until
 I reinstalled Linux, even after I stopped their driver from running, and I found a GitHub
 issue mentioning something like that, except when they closed the driver, it went away,
 so I'm not really sure what that's about. So yeah, I had some issues with it, both ideologically
 and when actually trying it, however, I will still put a link in the description, since
 if you're a Steam Deck user, I don't want to discourage you from trying it if you're
 okay with the telemetry stuff, because if it's good software, it's good software. The
 only real way to go from there was to write my own software, so that's exactly what I
 did. Luckily, the hard parts, getting the data out of the gyroscopes in these glasses,
 was already done by Tobias Frisch on GitLab, which I really appreciate him doing and making
 open source and being respective and fixing the issue that I made regarding really high
 CPU usage. It's excellent, and if you're planning on doing anything with these glasses, I highly
 recommend it. But yeah, he had already made that, so my job was only really to do the
 visualisation, to put a virtual monitor in an environment and have a camera that moves
 in relation to how your head actually moves. During that, I ended up making a members-only
 and Patreon-only video which was just me rambling for 50 minutes about the state of
 things as of the 12th of April, but I will give you a general rundown right now. It started
 with me wanting to use Godot, because I thought, well, it's a game engine, it should provide
 me the ability to render things, and then all I would need to do is somehow get the
 data out of the driver and have a script in Godot that is just constantly matching the
 camera's rotations to the rotations provided by the glasses driver. However, I couldn't
 find a reasonable way to get screen capture working in Godot, and the only game engine
 I could find that would allow me to get video into it reasonably, even if unofficially,
 was the Unreal Engine, where I found a Gstreamer plugin that wasn't made for Unreal Engine
 5, but I ended up getting working for Unreal Engine 5 and Linux, so my plan was use a Python
 script to get Pipewire desktop capture going and Gstreamer within Python sending the video
 frames to shared memory. Then the Unreal program could use its Gstreamer plugin to get those
 frames from shared memory and put them onto a texture. Saying things like that makes it
 sound so easy, but as someone who was both unfamiliar with the engine and C++ and the
 glasses and everything, that was days of work and it was really awkward. The way I was getting
 the outputs of the driver into Unreal was not rewriting it in C++ and making it an actual
 Unreal plugin or anything smart. It was a Python script that was reading the standard
 output of the driver and saving that to shared memory again and Unreal accessing that. The
 problem is that the Python script to do that was very, very slow. Like, unreasonably slow.
 I know it's Python but I cannot explain why it was so slow. Luckily C basic file management
 reading and writing is not too hard, so I just went into the driver's source code and
 did it there directly and then things were going great and I managed to get a cube moving
 and then I turned that into head movement and Unreal succeeded. The only problem was
 it was a heavy program. It wouldn't run at all on my laptop's integrated GPU, though
 that's probably more Vulkan driver issues than actual difficulty to run it, and on my
 laptop's GTX 1060 it used about a third of it. My laptop was using, like, 40 watts of
 power just to be idle with the glasses display rendering. So after all of that I did a rewrite
 in just C++ using Raylib as my rendering manager so I didn't have to use OpenGL or Vulkan directly.
 And that made things light enough that on my integrated GPU it ran better than it did
 on my dedicated GPU before, keeping in mind also this works on the integrated GPU where
 Unreal didn't, but also it just made things just much smaller, you know, it's a few megabytes
 instead of this big Unreal project. And I think that my side of it was actually pretty
 successful. The only problem is I had issues with Pipewire desktop capture and I was just
 never happy completely with getting all of those issues solved along with the general
 social awkwardness of using those publicly, so I ended up leaving it there. Though it's
 still on GitLab and I'll leave it in the description if you want to take it further.
 Oh, and side note, if you're wondering why I didn't just use OpenXR because you might
 have noticed these are supported in Monado, why not just use that for head movement? I
 just thought that Monado seems like a pretty heavy and large dependency for something that
 isn't really VR, but I did bother trying Monado, both with Unreal and separately, so I should
 have video footage of me trying the XR Gears demo with them, it's actually pretty cool
 even if you wouldn't want to use them for VR. I have glossed over so many things, like
 thousands of words worth of notes, that are just small details, they don't really impact
 my conclusion much, which is why I've been willing to leave them out, but it really has
 been a very interesting time just trying to figure out the value proposition of these
 and trying to do my little software development to see if I could make them work for me, and
 I'm gonna be honest, originally I was planning on waiting and waiting and waiting until potentially,
 be it some firmware updates on these that could somehow improve them, or client-side
 software development like an official Linux app maybe, or the third-party drivers for
 it getting better, or whatever it may be, I was originally planning on waiting until
 these would be how I imagined them to be, but I realised enough of the issues are in
 hardware and enough of the issues are just that this really wasn't a worthwhile purchase
 for me, that I can sell these and recoup 90% of what I paid, and I think that's exactly
 what I'm going to do. They're very very exciting and interesting technology, and it was great
 to see Micro OLED in person, and it has been really interesting to try them, I just don't
 think that they're worth it for me. Despite that, if you're a Steam Deck user, or if you're
 a Mac or Windows PC user that also doesn't mind the social aspect so much and you just
 want a larger display, and you don't care so much about people seeing the glowing bits
 in your eyes, if I were to have these plugged in I'll plug them in now, if you can get over
 those parts and you're happy with not really AR, just floating desktops, there's no head
 tracking, they are just 3 degrees of freedom, they definitely could be great. It's just
 that for me, the Android app offered nothing at all of value, and the DIY Linux route just
 didn't end up working. Luckily though, despite my time with these glasses not being particularly
 awesome, there's a group of people who I have to thank now who always are. A huge thanks
 to the supporters Ducky!, Russell Willis, pt1997 and Pytech, I really appreciate it, you can
 join them on Patreon if you'd like to, hopefully you've enjoyed, and I'm off to sell these.
