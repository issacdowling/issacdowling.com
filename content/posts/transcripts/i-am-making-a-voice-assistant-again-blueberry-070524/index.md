---
title: "Transcript: I'm Making a Voice Assistant (again)"
date: 2024-05-07T23:47:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---

﻿ It's been well over a year since I last talked about the self-hosted voice assistant,
 and since then it's gotten a from-scratch rewrite, a bunch of new stuff, and a new direction.
 But if I'm going to talk about it, and you're going to understand,
 I should probably catch you up with what's changed.
 The goal from the beginning has been to be open, not reliant on any company's
 proprietary technology, and not reliant on the internet except for where absolutely necessary.
 And at the start, those bits were all actually being handled by some other project.
 I mean, I was writing the apps, you know, the bits that would do maths or control my lights,
 but the thing that was actually getting my voice input, shuffling it between all
 the different services necessary to actually make my apps work, was a project called Rhasspy.
 And that was really useful since it meant I only had to deal with the user-facing things,
 and all of these complex bits that I didn't understand yet were being handled by someone else.
 As has been shown, it worked, and I used it as my primary voice assistant for a long time,
 and it was great. But the way that I was building things was getting
 hard to scale and kind of awkward, so I was like, okay, I'm going to do a rewrite of my own stuff,
 let's see what's changed with Rhasspy so that I can keep up to date.
 And it turns out, nothing had. And in fact, at this point, the main Rhasspy project has not
 been committed to in over a year, and no changes that matter to me have happened in years.
 Even Rhasspy 3, which I thought was poised to be some big change that was meant to be
 re-architecting of everything and it was going to be great, was left in an unfinished state.
 So I was left with no updates, and I was kind of hoping for more features.
 Okay, so fork it yourself, it's a community project, nobody owes you updates.
 I mean, you are right, and it's actually amazing software, and I'm really impressed that it has
 gotten me this far. It's probably the only reason that I actually began the journey that has led me
 to where I am now. It's just that most of the effort going into it seems more focused on the
 home assistant, voice assistant side of things, which I'm not really super interested in right
 now. And just looking at the language breakdown of the Rhasspy project alone, I know that especially
 a year ago me is not ready to tackle that. So it's not time to fork it, it's time for a from scratch
 new project, which definitely feels empowering, but also pretty daunting given there's been this
 whole layer of magic that I've just been able to rely on some other projects to deal with.
 And now it's my responsibility, which definitely led to mistakes. In fact, when I first thought of
 this idea, I just sat on it for a few months. But later on, it came up on my Discord server, and
 I ended up talking about the possibility of doing it for real with confusion unknown.
 And moments later, productivity was happening. Excalidraw, planning things, giving things names,
 all very productive stuff. And at the start of it, I was being productive too.
 But nearing the end of that phase of the project, I just wasn't. I mean, I'm not a classically
 trained developer. It's mostly self-taught since GCSE computer science only needs you to learn the
 very, very, very, very basics of Python. And that's about it. So for most things, I have just relied
 on learning things as I have needed them in my own projects, which means splitting big projects up
 into multiple files and that kind of thing and working together, I was not very skilled at. And
 I wasn't really capable of keeping the whole project in my mind at once and started to lose
 track of how things interacted with each other. So I ended up talking around Christmas time
 about the possibility of quitting. I mean, we'd gotten pretty far, but I still had nothing actually
 to show for it. If I'm incapable of working productively on this and there are other projects
 that might kind of be able to fulfill my needs, maybe I should just go there. We talked, I stepped
 away for the night, and I came back in the morning with a game plan. I'm going to build this badly,
 but functionally, and then we can make it better. And it worked. My motivation was not only back,
 but I had a functioning voice assistant at that point. Still not a great one. I hadn't figured
 out yet making things modular and all of that, but it was actually a working thing. I just took
 all of the work that we'd been doing before that was trying to make things really proper and done
 really well. And I was just like, let's just smush this together into one program, one single file
 that just actually functions. So I could finally wrap my mind around the whole project at once,
 and then I was able to build off it and we got things going again. And so things were restarted,
 first from the Rhasspy version, and then I tried to make the new Rhasspy version, and then we had
 blueberry as its own project, and then we had blueberry micro because the original goal was
 keeping the scope way smaller. And now the scope is actually bigger than normal blueberry ever was.
 Hopefully if you're in a similar position right now with any software development things,
 maybe that might be a good way to look at it for you, and hopefully this will help you too.
 So momentum was fast, progression was great, and although there were lots of individual
 decisions made at this time that I could go over, I think the most useful thing to do at this point
 would just be to show you where we are. Where first I want to show that yeah, it does do the
 basics. And this should only last 30 seconds, but I will leave in if it gets things wrong,
 particularly the wake word blueberry doesn't seem to go off straight after I have a conversation
 with camera, so we'll see how this goes. Blueberry. Blueberry. Make the door light red.
 Turning the door light red. I can use a different wake word. Hey glados. What's eight times 12?
 8 multiplied by 12 equals 96. I can use an instant intent to just ask what's the weather?
 And for that I don't need a wake word. Right now it's 16.0 degrees celsius and partly cloudy.
 Or I can ask for a timer. Um blueberry. Blueberry. Set a five second timer.
 Sure thing. I'll start a five second timer. And then to stop it I'll use a
 different wake word. Um once it starts going off. Hey glados. Stop the timer.
 All right I'll stop the timer. That was a super basic example of things that I didn't want to cut
 so you can kind of see there are still rough edges especially around the wake words but the response
 times are actually pretty decent. The the main value here obviously isn't that it can do these
 super basic things but it's that I think it's really easy to develop for and you can write it
 in any language. I'm working on a python module that should make setting things up in python much
 easier. There should be less boilerplate but it's language agnostic since it just communicates over
 MQTT. Just covering things kind of broadly, all you need to worry about when developing a core
 or an app for blueberry is you need to make a program that identifies itself. It outputs a name
 if you launch it with dash dash identify true and then you just need to set up some intents.
 For example using the increment volume intent from the volume adjustment code that lets you
 adjust the volume we have a list of keywords we have two lists of keywords and just one thing from
 each list needs to be spoken so I either want to increment or decrement and then I want some form
 of volume word in there to know that yeah I'm talking about the volume not something else.
 From there we go to collections which are some blueberry provided though you can make your own
 as well collections of these keywords so here we just want to look for any number so you need
 to say you want to increase or decrease the volume and by some actual amount and only on the condition
 that all of the tests you outline in the intent and there are other things as well like you can
 supply prefixes or suffixes that the user needs to say that there are a bunch of other ways to
 customize things but as long as all of the tests that your intent supplies match your code will be
 ran and then you can just publish a message over MQTT to say this is what I want the voice response
 to be. Your program can be whatever you want. Actually producing that speech that your Core
 asks for is done by Piper which is a really fast and pretty decent sounding local text to speech
 option and then the actual the speech to text when you're speaking to the voice assistant is done by
 OpenAI Whisper but not through their API it's done completely locally and you can pick with both of
 them different sizes of models and just different models in general that might in the case of text
 to speech maybe sound better but be harder to run so if you've got more powerful hardware and then
 for Whisper you can pick a bigger model if you've got more powerful hardware and you want
 it to be more accurate or you can pick a smaller model that will be less accurate but work better
 on lower end hardware. There are plans for a web UI for easier setup which actually reminds me you
 can go to issacdowling.com/blueberry if you want to see the docs and capital c conversations
 which should allow multi-step conversations with Cores rather than just do this thing okay done and
 since the whole project is under the AGPLv3 you can fork it you can modify it i'm fully open to
 suggestions if you think that this is an interesting way of doing things please look at the code send a
 merge request on gitlab go on the discord server and tell me what you don't like about it tell me
 what you love about it um i'm really really interested in knowing what other people
 are interested in plus obviously i have grander ambitions eventually a mobile version would be
 really nice and i would like to more concretely lay out how handling multiple speakers running
 off the same compute box like a server um should work and if all of that sounds familiar to you
 yeah this really is starting to feel a lot like Rhasspy isn't it which is a realization i had kind
 of halfway through or halfway between uh this new stage of the project and now which if you've
 developed software before yourself is probably a pretty familiar feeling just looking at a code
 base and being like why would you do it like that and then doing it for yourself and being like oh
 that makes a lot of sense um really like i i think of this as both a spiritual successor to Rhasspy
 but also because it's done by someone who's realistically much less good at programming
 than the original devs just a really fun project where i can learn things and hopefully give some
 use to some other people as well if you're enjoying the videos a lot you can join ducky
 and pt 1997 down there by joining on patreon or youtube memberships um i really really appreciate
 it so thanks a lot to those two um or you can just subscribe on youtube um if you think i've earned
 it hopefully you've enjoyed please just just give me feedback even if you're not a developer i would
 just really like to know what people think about this project um and hopefully you've enjoyed i'll
 see you next week
