---
title: "Transcript: Reverse-Engineered Software is Cool"
date: 2024-04-02T19:20:00+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
Nintendo's legal creativity as of late reminded me of something.
 I mean, emulators are one thing, but tons of my own tech rely on reverse-engineered solutions
 to problems that the manufacturer has made. And all of that's really cool,
 so there are chapters in the playback bar, let's get to it.
 Where we're gonna start with earphones. Which… earphones? What are you even…
 Well, Sony has an app that lets you control the different functions on them, like
 being able to change noise cancelling mode and strength,
 what the taps do for play and pause or controlling the assistant, that kind of thing.
 And although you might not want to access that all the time, you are gonna at least
 want to do it once so that you can get everything how you like it and then you can remove it.
 The problem with Sony's app, though, is that it's rubbish. I mean, it works,
 that's great and that might be all you're looking for, but when you hear Linux users talk about
 bloat in software, you might be used to kinda tuning it out because we exaggerate a lot, but
 this earphones app
 has achievements, accounts and… ear pictures, Sony?
 So what's a boy to do? I mean, if only someone else knew how to talk to the earphones and made
 their own app to do it but without the fluff. That's Gadget Bridge. And it's not the only
 program we're gonna be looking at today, and it's not even the only function of Gadget Bridge,
 it's like one of a million different devices it can talk to. And it's an example of looking at
 something super basic being done wrong and implementing it in just a better way.
 If that sounds familiar, I did recently talk about
 open apps and open APIs and how those are helpful because they allow this kind of thing,
 but the difference here is that Sony played no part in allowing this functionality to happen.
 And okay, why would they? All the app developers have to do is read up on the protocol they use
 to talk to each other, implement something that conforms, and go, right? No. Instead,
 they have to use the official app, awkwardly and at length analyse the communication between it
 and the device, and then try their best to figure out what's the best way to do it.
 What does what and make something that works. And that just makes no sense. Especially for
 accessories like this, where there's no security implications to being able to have more access to
 it, I really don't see any argument for just not releasing these kind of things. Like on an iPhone,
 for example, Apple does have a legitimate argument that more untrusted software running on a phone
 is more likely to lead to security vulnerabilities. I don't think they go about
 stopping that in the right way, but they're at least vaguely
 on the right train of thought. Earphones, though? I mean, evidently it doesn't actually stop
 anybody, because the tech community is amazing. It's just a shame that people have to waste their
 time figuring these things out when the tech companies already know them, they just don't share
 them. And it's even more impressive, given that, that we often end up with better apps than those
 made by the official manufacturers. And an excellent example of that is with RGB. Isn't that
 cool? I mean, I've talked about other projects like WLED in the past, where the whole thing is intentionally
 very open and you can control it with whatever. But that doesn't mean that's all you can control.
 I mean, sure, you saw that I had a Logitech keyboard and a Logitech mouse, so I could just
 use the Logitech software. The problem is, it's really rubbish, and there's an alternative,
 OpenRGB. They too have a document about reverse engineering things, just like GadgetBridge.
 But I think OpenRGB might be a better example to use when talking to you about where reverse
 engineering goes wrong. I mean, I love the software, and for the vast, vast majority of
 things, in fact, I only know of one situation where anything has gone wrong, for the vast
 majority of things, everything is perfectly fine. But if you're creating a spec and learning about
 how devices function by kind of very, very, very educated guesswork, there are chances that you
 send the wrong commands to things that you're connecting to. And there was one time where,
 accidentally, OpenRGB was bricking MSI Motherboard's RGB controllers.
 That wasn't a widespread thing, it got fixed, and obviously, most things don't have that issue.
 But it is important to remember that, at least with the reverse engineered protocols, these
 people aren't working off a set spec sheet that says "this device can do this, and this is how you
 do it". That has the counter, though, that if the original manufacturer was given wrong, out of date,
 or just chose not to use all the features in that original documentation, you might end up reverse
 engineering something, only to find out it has more features than you originally thought. Like with Ryzen CPU coolers with OpenRGB.
 I'll leave a link to that podcast section in the description.
 RGB is meant to be fun, and what's not fun is having either half of my peripherals doing
 different things to each other because Big Company X won't talk to Big Company Y.
 And lacking interoperability does benefit the one company that you're locked into,
 if you choose to spend all of your money with them in the future so that you can have everything be
 cohesive. I would argue that it's in the best interest of most manufacturers to be interoperable.
 For every one winner that there is,
 there are the hundreds of other companies that didn't win, and they can get some business rather
 than none. Luckily, some companies do recognise that, and as far as I understand it, some will
 help OpenRGB or at least send over hardware to get their products into OpenRGB. But I think that most
 of OpenRGB is still a reverse engineering effort, and yet it's still better than any
 proprietary RGB software I've tried. Again, the community effort is great,
 it just really shouldn't be necessary. But it is. Because even if we want
 official support eventually, software companies often need to see the better solution in action
 before they're willing to implement it themselves. A great example of which being the Steam Deck and
 its use of wine. Proton. Wine. Basically, we on Linux needed to run Windows programs,
 but we didn't have Windows. And virtual machines, although fairly well established,
 aren't the best solution for that, both in terms of complexity, like you don't want to be setting
 up a whole virtual machine for one app, and the fact that they don't integrate
 well with the host install typically, like having a Windows app available in your right-click to
 open with menus. That's not to say solutions like that don't exist. For example, compatibility is
 just a lot better in virtual machines generally, so some things do work with that, like Microsoft
 Office, there's an example on screen now. But generally, it would be nice if we could just
 find a way to make those Windows programs think they were running on Windows. Not by taking code
 straight from Windows, since Microsoft would be on that real quick, and
 we would struggle to get the code anyway since it's not open source, but instead by just watching
 what Windows does, and you can probably tell, I just keep describing what reverse engineering is,
 so I'll stop. We make wine do what Windows does, but on not Windows. And that's important,
 I didn't say Linux. Wine works on BSD variants, macOS, and Linux, I think even on Android,
 even though that's really just weird Linux. And although I'm sure all the Linux users in my
 viewers, which is probably actually a significant amount of you given the results of this,
 poll I gave, I'm pretty sure all of you will have seen a program running under wine crash,
 and just find some things just don't work, but it works remarkably well for something that has had
 no help from Microsoft. And you can combine it with the technologies that are native to the
 Linux platform, like Flatpak, if you want to sandbox it, and then you can have all of the
 benefits of the actual native Linux solutions and all of the software availability, or at least
 a lot of it, for those less nice ones.
 I might actually end up testing how well Wine works on non-Linux OSs,
 since I'm considering moving temporarily, even if it went well, I would not be switching, but
 temporarily making a video about how gaming on FreeBSD would go. So let me know if you're
 interested in that. I think it could be cool. Like VR is meant to be. HTC used to work
 closely with Valve so that you needed no additional software besides SteamVR to just
 run it. But as of late, they've started switching to using their own software,
 which then connects to SteamVR or whatever else you're going to use.
 That, for Windows users, means settings split between different places,
 more complexity in general, which leads to higher chance for failure. And trust me,
 there are failures. And all of that will come with much more performance overhead than just
 doing things all in one place. But is that because HTC had some amazing new feature coming that they
 could only do if they handled all of the software themselves? No. As far as I can tell, it really
 was just HTC not feeling like it.
And that means, I mean, you know, at least Windows users have a worse but
 still functional experience. Linux users are left with nothing because HTC doesn't care about Linux.
 But precisely because it's just the same but better, someone took the old driver,
 made modifications to it, and released the Vive Pro 2 Linux driver, which,
 although clearly focused on Linux, used to build on Windows. And I want to look into actually
 using it on Windows again, because I'm having some v-sync to photon latency,
 weird, complicated issues that it seems like no one else is having on Linux. But gosh dang it,
 besides that, it has brought this really, really annoying headset to get set up,
 to something that works just like it used to. Plus, if you want a fully open stack,
 there's Monado, which is an open source OpenXR runtime. It has basic support for my headset,
 but much better support for older ones. And it has some tracking issues right now,
 so it's not there yet, but I'm really rooting for it. And VR as a whole just seems much more open
 than previous new technologies, and I think a lot of that is thanks to Valve and SteamVR. I mean,
 they're not an open source company, but they contribute a lot and do a lot less to get in
 people's way, so I really appreciate that. However, obviously, I'm rooting for the fully
 open solution with Monado. People even get Oculus headsets working with these open source drivers,
 and Windows Mixed Reality. And although I can't show it you today, since I'm still waiting for
 the hardware to arrive, there are even reverse engineered Linux drivers for AR glasses. So join
 the Discord server and get subscribed if you want updates on that. Hopefully you've enjoyed, huge
 thanks to the Patreon supporters Ducky! and pt1997, 1997, still not sure. Hopefully you've enjoyed,
 and bye.
