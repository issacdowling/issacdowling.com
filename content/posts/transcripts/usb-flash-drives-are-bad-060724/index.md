---
title: "Transcript: USB Flash Drives Are Bad"
date: 2024-07-06T19:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Trancript"]
draft: false
showTableOfContents: false
---
 Quick, I really need to upload something, but the internet's down.
 How can I get it to my phone so I can use data?
 Don't worry, I've got just the thing.
 I'm never asking you for help again.
 Because USB sticks do have a time and place, but it's not now or anywhere near sensitive
 data.
 They're unreliable, easy to lose, and just so last decade.
 But not everyone wants a NAS, so what are the different ways we can move data around?
 We'll start with my favourite.
 Airdrop?
 I doubt there are many Apple users watching these videos, and if you are, you know about
 Airdrop.
 And Android does have something similar, called Nearby Share.
 It's just that... nobody cares?
 Like, nobody has ever tried to share a file with me that way, and whenever I try to do
 that with someone else, it's either that it just didn't work and we don't know why, or
 that one of our phones didn't support it.
 Can it at least sync to a computer?
 Obviously.
 As long as it's an x86 Windows computer with a special app on it where you need to sign
 in with your Google account.
 So not very convenient for sharing to random people.
 Enter LocalSend, which is super cross-platform thanks to Flutter, so that's Android, iOS,
 Linux, MacOS, and Windows.
 And the best part, you don't need the other person to have the app.
 I mean, ideally they would, because you get a cute little nickname and things just kinda
 look a bit nicer.
 But you can as well just start a local HTTP file server, which supports encryption in
 transit and also authorisation, so whenever someone tries to connect, you need to press
 a little tick to say okay, so you're not just blasting it out to everyone on your network
 in case you're doing this at school or work.
 I won't pretend it's as magical as Airdrop, since you do need to be ready to receive a
 file with the app open or connected to the link, rather than just being able to airdrop
 and swoosh it over to your other device or someone else's if you're in their contacts
 or whatever.
 However, I use it heavily, I use it very often, it has been reliable, it has worked well,
 and so if you're not the NAS type, but you want to transfer files either without a wire
 or you've been doing it with USB sticks this whole time, maybe this will get you off that.
 But some people are looking for something a bit more permanent than that.
 So if you're completely uninterested, you can skip to the next chapter, but if you're
 on the fence, hold on a sec.
 It doesn't have to be complicated, there doesn't have to be some secondary machine running
 24-7, and you don't have to maintain any special environment to make it work.
 Because I think there are two types of people when it comes to NASes.
 Like if you think about the last thing we covered, LocalSend, we're not actually needing
 permanent access to some set of files, we just need some form of go-between so we can
 access things from, or send things from one device to another.
 And if that's all you need, you can just use your existing machine.
 If you're on Windows, you can just right-click a folder and share it to the network.
 And same goes for Mac OS, and same likely goes for Linux, you'll have to check based
 on your environment.
 However, even if you are looking for constant access to the same group of files, it doesn't
 need to be expensive or complicated.
 Obviously I would like to advocate for you all to have some Linux machine running RAID 1
 hard drives, so duplicates of everything on both drives, so hardware failures aren't
 going to affect you unless a power supply explodes everything.
 In a perfect world, everyone would be doing things perfectly.
 However, all I actually want from you is better than a USB drive.
 And even some old laptop is probably going to offer that if you swap in even a used hard
 drive.
 It's going to be faster, cheaper per gigabyte, and more likely to be more reliable than most
 USB flash drives.
 And it would be one step closer to being correct, even if obviously I should say, yeah, one
 drive is going to fail.
 Eventually all drives are going to fail, so you still want backup somewhere.
 If you need some help, but you're decent with searching things, if you're looking to connect
 to a NAS, you can search for mapping a networked drive on your OS, and that should find it
 for you.
 And if you are interested in a dedicated machine and doing things a bit more properly but don't
 have much experience, TrueNAS is definitely a place to look since it has a nice fancy
 GUI that should be a bit more friendly than just being thrown into a terminal.
 Never.
 I've got my USB stick, it's got USB-C on one end, USB-A on the other, it's magical, you
 will never move me to anything else.
 And I mean, I guess that is fair enough.
 For some people, the effort of going network attached or even using an app to do things
 just isn't worth it.
 So I want to at least talk about a few ways you can make the experience using a USB stick
 a bit safer and a bit nicer.
 The first is encryption.
 It's easy, so just do it.
 On Windows, it's just in a right-click menu, though that is limited to just the fancier
 versions of Windows because Microsoft reasons.
 There is third-party software to do it, but I can't vouch for any of it.
 In Mac OS, you can just use the disk utility.
 When you reformat a drive, you can say make it encrypted, and in Linux, it will be somewhere
 in your GUI file managers, again, when reformatting things.
 That changes losing a USB drive to, oh, I lost the hardware, rather than, uh-oh, someone
 might have my NDA data or they might have this half of a shoot that I've completed.
 The second and third things I've got are copy instead of cut and try to keep multiple actual
 physical drives with you.
 I have lost the audio for a shoot due to a dying SD card, and I have lost college work
 due to a dead USB drive, along with not losing data because I was careful, but I've had many
 like tons of micro SD cards fail, and a few more USB drives fail.
 These kind of things just are not reliable enough for you to trust them as a single copy
 of things, and if you cut and paste something, it's getting removed from the drive you're
 pasting it from as you put it on this, so if it gets slightly unplugged or if it were
 to fail during a transfer or whatever, you no longer have the original copy to go back
 to, and I try to make sure if I'm actually taking data somewhere, and it is to be on
 one of these, I make sure to have multiple drives with me in case one of them fails during
 that.
 It's not like these kind of things are super likely to go wrong at any given moment, it's
 just you don't really tend to think about upgrading USB sticks or, you know, keeping
 them in a healthy state, and it's not like you know when they're going to fail, so having
 them fail can put you in a really awkward situation, and it's inexpensive and easy enough
 to just go, I'm just going to bring two of them.
 But maybe actually the least and most obvious thing to do is to use your phone.
 If you're on iOS, I guess this probably doesn't apply to you unless things have changed, but
 I don't know about you, but I have way more storage than I actually need on my phone,
 and the storage in my phone is actually fast and reliable, unlike what's on most USB drives.
 It's got USB 3, I don't need to worry about it blocking all the ports next to it because
 I can just use a USB-C cable rather than having a thick drive that can get in the way.
 Using my phone as a USB stick is far more convenient than actually bringing a USB stick,
 and it's something that I just hadn't thought of before.
 That by itself almost completely kills USB sticks for me, because I'm always going to
 have my phone, I or someone around me is always going to have a USB-C cable, and it's just
 a better experience.
 But as mentioned before, I do keep a couple, literally two, of these around still for their
 remaining use cases.
 If a friend comes to me for tech support with a malware-stuffed laptop, I would rather keep
 my devices air-gapped from that, or if I want to install FreeBSD, like I did two videos ago.
 What else am I going to use?
 A CD?
 I mean, if you have a Linux phone, or probably a rooted Android phone, you can actually use
 some USB magic and use your phone as a bootable device, but generally you're going to be using
 one of these.
 The actual idea for this video in the first place came from the fact that I was doing
 some tests in college recently, and I do them digitally, and they were being saved to some
 ancient like super thick 8GB USB 2 drive that Windows kept saying has errors and they need
 repairing, which is super cool.
 And the fact that I had been revising and then doing tests is part of why this video
 has been so short, and I'm very sorry for that, but I think we'll end things off by
 checking what's on this drive.
 Oh yeah!
 It's the supporters, I hope I can manually change this focus in a way that works.
 It's the supporters that I need to give a huge thanks to, to Ducky, Pytech, PT1997,
 and Russell Willis.
 I really appreciate it, you can join them on Patreon or YouTube memberships if you would
 like to.
 I really hope you've at least found this video useful, even if it wasn't super the most
 amazing one, and I will see you next week, or maybe two weeks, but I hope one week.
 Thanks and bye.