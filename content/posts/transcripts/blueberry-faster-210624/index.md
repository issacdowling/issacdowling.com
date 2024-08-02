---
title: "Transcript: Blueberry Just Got Way Faster"
date: 2024-06-20T08:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
 A-L-E-X-A is boring and proprietary, where Blueberry is open source and way more fun.
 However, Alexa works, and Blueberry is still in development.
 So in this episode, we'll see that a few of the core tools got rewritten in Go and made way
 faster, partially because of Go and partially not. It got music support, and a few little extra
 things, including something that makes it way easier for other developers to make apps for it.
 Those are all in the chapters below, and let's get to it.
 And we'll start with the speedup that's most likely to impact the biggest number of people.
 It was nothing to do with a big architectural change or
 a rewrite or anything. It was a 20-line change that brings latency from this:

 Hey GLaDOS, what's 12 plus 3?
 12 plus 3 equals 50
 To that
 Hey GLaDOS, what's 12 plus 3?
 12 plus 3 equals 50

 Which, for many, probably brings it from unusable to pretty alright.
 But what was causing it, and why didn't it show up when I demoed Blueberry for you in the last
 video? Did I cut out the latency between me talking and it responding? No. However,
 I do all of my development and testing on my computer, my desktop, which, although not
 the fastest thing in the world literally, it's pretty fast especially single-core, it's Ryzen 7000,
 which means a lot of little bottlenecks just kind of get brute-forced through,
 and I don't notice them until I test them on my laptop, and that was when I noticed this.
 And what was surprising was, of the two things that I don't have control over,
 it wasn't transcription, it was text-to-speech. Text-to-speech? That should be ridiculously fast
 even on a Raspberry Pi, so what's the deal? Well, the way that I'm doing text-to-speech is by
 launching the Piper text-to-speech command line application, like an actual other program. Python
 is launching that and dealing with the file that's outputted from it. So, although it's not like my
 laptop has a hard drive, and although even for a hard drive 100 megabytes is not a ton of space,
 if we're closing and opening that program every time we need to process a request,
 we're having to reload that model every time we need to use it. And maybe the Piper CLI program
 is doing other things on startup as well, it's checking things, maybe it's not actually taking
 a long time to generate the speech, but it's taking a long time to prepare to generate the
 speech. So, when I noticed these slowdowns, that was the first place I went and checked.
 And, like I said, near the start, it was a 20-line change. The reason I didn't use the
 Piper Python module at first was just because I couldn't find any docs for it and I didn't think
 "maybe I'll look at how the Piper CLI does it", but then I did think that. And now the latency is much
 better, which is kind of sad that it was just some little mistake that I'd made rather than
 some big cool thing that I got to rewrite, but at least it is an improvement.
 Next, music.
 Blueberry. Play music, but it's not actually music.
 🎵Beep boop, this is a music track.🎵
 And if you're willing to imagine that was music, that was music.
 But how hard was it to make that work? Surprisingly, not very. However, because
 Blueberry isn't some commercial project or a job, realistically, I cannot dedicate
 tons of time to integrating with a bunch of third-party services and making sure they keep
 on working. So, realistically, either I would end up making all of those, so, you know,
 integrating with Apple Music and Tidal and YouTube Music and Spotify and so on,
 and then they would break over time, or I just wouldn't make them at all.
 The way that I've gotten around that is by using an intermediary called Mopidy. As far as I
 understand it, Mopidy is a music server, but that doesn't actually provide or handle getting any of
 the music itself. However, you can make plugins for it that provide the music. So, if you want
 Spotify, Mopidy Spotify. You have local MP3s, Mopidy Local, etc, etc. With that, you can connect
 your thing to Mopidy, which is a local program, you don't need to worry about external services,
 and I can connect to Mopidy, and it works. Plus, it seems like Mopidy is the tool of choice for
 interacting with music things in the open source community. So, if you want a bunch of extra things,
 hopefully Blueberry will be able to integrate with it, and if you don't, you can just set up
 Mopidy, only use it for whatever music service you want, and it will just be working as a go-between.
 And what I want is to talk about Go, both directly what it means for this project,
 as opposed to Python, and what technically would have been possible before, but was made way easier
 by Go, which is where a lot of the re-architecting decisions came from. Whether you see it as being
 wise or just permitting bad programmers to still use it, Go's simplicity is incredible to me at
 least. Like, I have very thoroughly enjoyed the fact that although there are a few kind of weird
 things about using it, there is none of the C++ look to code with Go. Everything is just very
 simple. There aren't a ton of symbols everywhere, or a bunch of weird features that mean different
 things in different contexts. Like, it's just Go, and you will use it to solve your problem,
 and there won't be weird specific things that you have to do in weird specific situations. I have
 really enjoyed that. Besides when working with nested JSON objects, I haven't written a single
 bug that has been completely mind-breaking to figure out and then fix, and the only issue I
 was having with nested JSON objects is the fact that I didn't really understand how interfaces
 work. Everything is just super easy to read, and it's super easy to deal with dependencies.
 I thoroughly enjoy that everything is statically compiled. When you go to compile something and
 you don't have a dependency for it, it will pick it up for you. I don't need to mess with
 virtual environments, and I don't need to mess with my system package manager.
 Plus, although obviously it's a compiled language, compile times are so fast that
 prefacing a Go project with Go run while developing feels just as fast to start up
 as prefacing a Python script with Python. And while writing that code that I want to run,
 the Go LSP is the most helpful I have ever seen. It seems like it's ridiculously smart without the
 need for AI stuff, and it's just instant. And I really enjoy that although it might be kind
 of awkward that it's very opinionated about things, it styles the code for you. You don't
 need an external tool for that, and that just means everything is really consistent between
 your projects and other people's projects or everyone on your team. Go just makes everything
 really easy. The only external dependency I even have is the MQTT library because the standard
 library is full of just really useful things. Working with errors as values as well instead
 of having exceptions that could just pop up anywhere and try catching those is just a new
 way of thinking about errors for me, and it's just kind of stupidly intuitive. I can see every
 single function that might return an error, and I can choose to yeah maybe ignore it, or maybe I
 will panic on it, or maybe I will actually handle it, but at least I'm making a conscious decision
 to at least do one of those wherever an error could occur in my code rather than just having
 try catches or try except and getting confused by what actually raised it. It's just it's really
 enjoyable. I'm not going to linger on Go for too long because this is a Blueberry video,
 but I just wanted to say I think Go might be my new favorite programming language. Obviously I've
 not tried that many so far, so maybe something else will replace it in the future, but I'm
 extremely glad that I decided to give Go a chance for this. What Go has actually meant for the
 project primarily is willingness to do concurrency. There's only actually one place in the orchestrator
 where I have used concurrency, and you know I won't pretend that I know more than I do,
 but what I will say is that async in Python makes me kind of sad. Multithreading in C++,
 and I understand there's a difference between asyncio and multithreading, but multithreading
 in C++ is very error-prone but also at least makes sense to me, and Go seems to combine both of those
 for me. It makes a lot of sense for me and it provides me ways like channels to not error
 myself into oblivion. So the way that's affecting things, even though again these aren't bits that
 I had to write specifically for concurrency, they just kind of happen that way, is MQTT requests.
 The orchestrator used to have to wait for all cores to be set up for it to actually start itself
 up, and the same went for the intent parser. And the reason that was the case was because every
 subscription to an MQTT topic was blocking, like I would subscribe, block, and then when I got a
 response I would deal with the response. So that meant each core would have a role and it would say
 I'm going to give you some intents but no collections, say, and then the orchestrator
 would go "okay I'm gonna get all these intents, I'm gonna get all these collections, once I've
 got them all I can move on." If a core failed the orchestrator could not start up, if a core took
 forever to send something the orchestrator would take forever to start up. Same again with the
 intent parser. Now I don't need those roles, which means, which is where the actual concurrency that
 I did write begins, instead of having to launch each core, request its roles, parse those, save
 those, then reopen it as normal, I can now just launch a core and that launching of cores happens
 concurrently which makes it a bit faster even though it's really basic. But also besides that
 it means that the orchestrator can just start up and in the background, that was a really weak
 snap, the orchestrator can just start up and then whenever it receives something to deal with it
 will deal with it in the background and everything's all good. So if you were to write a core that took
 15 seconds to start up, because I don't know, but it does, the previous way would mean that
 everything takes 15 seconds to start up and you can't use it until then. Now everything else will
 work until your core, because your core is the only thing doing work and when it's ready it will
 tell everything else that it's ready and it will be able to join the list of intents that can be
 used. And like I said I am 100% sure that could have been done in Python and with the concurrency
 with MQTT stuff, you know it's actually the MQTT library that is handling making a Goroutine for
 each of those things, it's not even me, I'm well aware that it could have been done without Go.
 It's just that Python kind of pushed me away from it and I couldn't find a very easy way to
 learn async stuff where Go encouraged it. Okay so music was added, things were rewritten in Go and
 made a bit faster which by the way does not mean everything is 100% Go, you are still fully free
 and I still have some like Python cores or any other language you want, anything that can speak
 MQTT you can use that. But what else? I added a little utility core that I think you would just
 expect from a voice assistant so you can now say "Simon Says" whatever and it will repeat back to
 you whatever and I'm actually finally beginning to start work on that web UI that I mentioned in the
 previous video. The problem is I was originally planning on doing it in Svelte and I was like
 okay it sounds good, React can be kind of awkward with things and I've tried that a little bit,
 Svelte time. Once I actually got to working with Svelte though I think I enjoyed most of it but
 the bits that I didn't enjoy kind of made me feel like just dealing with React's problems. Maybe the
 easiest example of Svelte feeling kind of hacky and me realising that maybe React's way of doing
 things makes a lot of sense is that with Svelte unlike React you can just put a normal variable
 on screen and it will re-render when the variable changes and that's done because Svelte detects
 when you reassign a variable so variable equals something else but if that variable is an array
 and I do array.push to add something new to that array it's not going to update because Svelte is
 looking for assignments so instead I can do this array equals spread the old array and then a new
 item and they say you can do that for a bunch of other things it's like it feels like I should and
 I understand React is not normal JavaScript either but it feels kind of weird that I'm
 kind of writing JavaScript, kind of writing CSS and kind of writing HTML but not quite. React
 makes it much more obvious to me what are the weird React things and what are the regular things
 but then the reason I don't just go and do React is because it has its own set of problems. Primarily
 for me even though it sounds like a really bad excuse to just not do anything it's because
 React is I just don't understand it. I know that I could just make a blank React project
 and I know that analysis paralysis and just trying to figure out what the best thing is kind of stops
 you from learning when you should just pick something and go for it and figure out what's
 wrong with it later but it's kind of concerning that I don't actually know what like do I need
 Remix or Redux or next.js and I'm not even sure if those fit into the same category and I
 understand that a lot of these are questions that someone with some base amount of knowledge could
 quickly find it's one search away but for me there is so much going on with React and so much jargon
 that I just don't know where to begin and the only reason I've not just made a choice and tried to
 stick with it is because I don't even know what choice I'm making like I don't even know how that
 choice affects me let alone whether it's just the best one or the not best one.
 HTMX sounds very interesting and ideologically resonates with me but is also different enough
 from the norm that I would like to learn the norm's rules before I break them and vanilla
 html css and javascript also sounds kind of cool it just also sounds like it would probably
 actually be a hassle in the long run and make something that's not actually very good so I'd
 like to know what are you thinking honestly um as kind of awkward as it is the front runner right
 now is React Native because it's as simple to set up as Svelte like it's it's much more
 straightforward to get something React Native going but I still get the the good bits of React
 and I get the bonus of having a mobile app which I would kind of like beyond that tangent about
 web uis I'm actually now thinking about how to solve the problem of multi-step conversations
 unlike when I previous mentioned it when I was just like "I'll get to it one day" um and I would
 like to get reminders and alarms working since those are something I would actually really like
 to make a lot of use of from a voice assistant also I'd like to add this as a little bonus clip
 because even though it's something I mentioned in the intro I never wrote notes for it so I never
 ended up saying it in the main video when I mentioned being able to develop cores more easily
 for blueberry now that's because there is now a proper python package for blueberry so that should
 mean that now you can just instantiate like a core class a core object give it intents or
 collections or anything like that you can see all the fields that you can possibly give it and then
 just say core publish all and it has functions for waiting for your intent to be called and giving a
 response back so you shouldn't have to worry about all of the complexities of dealing with MQTT
 yourself this will handle parsing arguments for you hopefully that should make developing cores
 a bit easier and you can find it in the git repo and I plan on writing documentation for it soon
 I'm also trying to figure out how exactly interaction with a phone client should work
 and because it's similar logic just how in general multiple smart speakers connected to one
 server doing the processing should work I'm not sure the details of that yet but it probably
 shouldn't be too hard and I would expect to hear an update on that on the next video
 with that you can find the git repo and a discord server if you want to discuss it in the description
 and um blueberry thank the patrons um so a huge thank you to Russell Willis and Pieteek who have
 joined since the last video and obviously for the regulars uh I really appreciate it Ducky! and pt1997
 um I also really appreciate the fact that you waited two weeks for this video to come out
 um I really hope you've enjoyed um I'm very sorry that I lied to you I just used the spacebar to
 make the video behind me play um and subscribe if you'd like to I'll see you next week
