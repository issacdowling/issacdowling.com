---
title: "Transcript: Making my videos more accessible"
date: 2024-02-22T00:47:00+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---

﻿ Accessibility has a much broader meaning than I used to think it did, at least within tech.
 I used to imagine, when I would think about accessibility settings, things that would
 allow blind people or deaf people or people who otherwise could not use some form of technology
 to now be able to use it.
 But if you actually look in the accessibility settings on your phone, you'll find tons
 of stuff that's useful for everyone whether they can already use their phone or not, like
 panning audio left and right, dimming the screen extra far, or even just changing the
 font size.
 So let's have a look at how I can improve my own video's accessibility, based on some
 real-world feedback using the Fediverse, AI, and mostly much more normal stuff.
 If you'd like to look at any specifics, you can use the chapters in the playback bar,
 because first we've got some really basic stuff that takes creators very little effort
 but that can be helpful to everyone.
 Brightness and audio levelling.
 I mean, I'm not going to make all of my videos grey, but sometimes a screenshot of a white
 website can feel like a flashbang in a dark room, or nothing if you're in a well-lit one,
 so it's not like I want to completely ruin them and change them beyond recognition, but
 at my discretion I would like to make things more pleasant on the eyes.
 An example of where it wouldn't be relevant would be if I was shooting somewhere snowy
 or otherwise super bright, yeah your eyes are already adjusted, there's no point, or
 if I need to show you something as the original asset or source footage was, yeah I'm not
 going to modify it, but hopefully by changing things a little bit I can make things a bit
 easier on your eyes.
 If you watched my last video and didn't even notice, then yeah, a lot of the screenshots
 on that were turned down and seems like people were fine with it.
 Another thing that should help images that I show on screen be a bit nicer, and that
 I have actually been using for quite a while now, is I want to use Firefox's responsive
 design mode whenever I take a screenshot.
 That lets me enter a custom low resolution which will make all the elements on the screen
 quite big.
 Then I can set the DPR to 3 which means when I actually take the screenshot it will render
 everything at triple the resolution, keeping everything sharp.
 That should mean that everything is still legible whether you're on a big TV or a little
 tiny phone, and everything is sharp in all situations.
 Right now you can actually see an example of a comparison between my way of taking screenshots
 versus just taking a screenshot at my monitor resolution and zooming in in post.
 There's not actually a huge difference here, but I promise sometimes it's quite relevant,
 so hopefully this is worthwhile, and if you've thought that website screenshots look good
 in previous videos, it's because I do this.
 And if you think this is a lot of thinking about what screenshots should be like, I mean
 some people recreate the whole thing, like they'll find the font and do that so it's
 all high res and replace all the images on the web page with higher resolution ones or
 AI upscale them, and that's another thing that very very occasionally I will feel the
 need to do, but it's not part of my normal process.
 The previously mentioned audio levelling is very very simple, so I've got another audio
 related thing after that.
 But to get this done, all I need to do is be about to export a video, and tick a box
 that says export this with the audio normalised to YouTube standards.
 That should make sure that my videos never blast you with audio, or be the ones that
 make you have to turn it up so far that the next normal video is the one that blasts you.
 I've also in the past tried to make sure that my audio, at least from my voice, is always
 mono.
 I mean maybe at some point for a bit I might want to pan the audio left and right.
 But generally there's no point in doing that and things are more pleasant if I'm just coming
 from the centre.
 But the way I was doing that before involved recording in stereo, then manually going in
 right clicking each clip and setting the right track equal to the left track.
 That's problematic for two reasons.
 First, sometimes I would forget a clip and that sounds weird for you, but then secondly,
 it's an entirely manual process that means right clicking each clip and I forget whether
 I can do it in groups, I'm pretty sure I can, but I still have to do it when I'm importing
 whole batches of video, it just makes things more error prone.
 But then I remembered my mic has a screen.
 I can just go to the menu and set it to mix everything down to mono, as well as upping
 things to 48khz from 44.1 because why not.
 Speaking of the mic, I do hear you, one guy, that says I look ridiculous with the mic.
 And you know what, maybe.
 But it's kinda fun.
 This audio quality is way better than I could get out of any lavalier mic I could even nearly
 afford and it's just like a little mini podcast.
 I like it.
 Though I'm not interested in doing ASMR anytime soon.
 And now the fancy schmancy AI stuff, where at the request of a commenter I realised I
 should really be writing more blog posts, but I can't actually be bothered to do that
 so I'm just gonna get llama to do it all, hopefully fine with that.
 No.
 If you actually read the comment, sorry Elmar64, they say that as someone who speaks English
 as a second language, YouTube can be kind of awkward with how it handles subtitles.
 Since the quality of the auto-generated subtitles isn't that great even if it's mostly there,
 and that navigating through them with the player can be kind of awkward.
 So I posed a problem with their proposed solution, and an actual solution that I think should
 work for both of us.
 So yeah, writing blog posts would be great, and I actually would like to get to doing
 them again, though specifically with shorter things in mind that aren't really video
 worthy.
 But they take a lot of effort to do well, and that's effort that's duplicated, like
 it's not directly transferable, but I have to do a lot of work again if it's just a
 companion to a YouTube video.
 From both a growth and a motivation perspective, I'm gonna get nowhere writing huge, maybe
 very interesting, maybe very detailed blog posts that practically nobody is going to
 look at.
 However, I can use the website that they're on, issacdowling.com, there is a blog post
 already there, even if like I said the future ones are going to be smaller, I can use that
 website as a jumping off point for the way to fix things.
 Firstly though, we'll figure out improving the subtitles themselves, which, sadly to
 some people, and it is kind of awkward to have to go down this path, probably isn't
 the two most obvious ways, which is either writing them myself, or paying a third party
 subtitling service.
 Because I can't really reasonably afford that while I don't earn any revenue from things,
 which might have been the case when I wrote the notes for this video, but actually I do
 now earn a small amount of money from this, it's not from YouTube ads, it's from individuals,
 we'll get to that later, but not really enough to pay to subtitle all of my videos.
 And then writing good subtitles just takes a very long time, and going back to the motivation
 thing, I probably could, and I could probably sometimes during free time do that, but it's
 not something that I could do for every video on time, and that's kind of the solution people
 need.
 However, I do have access to open, free, machine translation.
 So I wrote a Python script, to which, if I really really wanted to, I could probably
 give its own video.
 I mean, it's not that complicated, it doesn't have a GUI yet, and even when it does, which
 it probably eventually will, I expect to keep using it through the CLI, but I even wrote
 myself a little help document for it, in case I forget, even though the whole thing
 is only like 100 lines long and pretty self explanatory.
 It gave me a nice chance to use a few things that I'd thought about before, but never actually
 put into practice, like making a Python program that properly takes command line arguments.
 This does that.
 Or, I had to look up how the actual file format for subtitles, .srt's, actually are formatted,
 and how I could make those in Python, before realising someone had already written the
 code to do that, which I now use instead.
 Or, something that I have used a lot, but just is another chance to iterate on it and
 learn about it, is whisper.
 I took a significant amount of code for whisper from the blueberry project, which is the self
 hosted voice assistant that I work on.
 And now that it's all made, which all in all took me a few hours, including a bit of iteration
 and cleaning up after the initial thing was completed, I now just have a script that I
 can feed a video to, and it will output a transcript, which is just the raw text, and
 an .srt file that I can just put along with a video and upload it to YouTube.
 But also, because I have that transcript, I now have issacdowling.com/transcripts,
 where every video will just get a text dump.
 It's not going to be well formatted, and I wouldn't expect most people to need to take
 advantage of it, but if you're just wanting to see the transcript of a video with no fluff
 added, and honestly, probably a few mistakes, even though I do do a human pass over it where
 I read over it quite quickly with the video sped up, I can't promise everything will be
 perfect, but a very good transcription of every video will now be available there.
 Which means that you now get better subtitles and a new way to look at them, and I get some
 inspiration.
 But what does that mean?
 What I love is making videos, and YouTube is the best place to do that.
 I can't foresee that changing for a very, very long time, and so that's where the primary
 source of video content is probably always going to be.
 But for any outside things, where I don't really need growth, it's just for if someone
 wants to talk to me or communicate to me, well, why not have those be open source, comfortable,
 and in a way that suits you?
 Like a personal website, and an email, and a mastodon, that's where the inspiration came
 from.
 So, yes, I'll be joining the Fediverse.
 The actual plan is for everything to revolve around my domain.
 Either things are going to be a Fediverse account and they will be at issacdowling.com,
 no matter what the username is, or they're going to be linked to from my site.
 That should simplify everything.
 If I am ever big enough that there are any weird telegram scams in my comment section,
 well you can know, is it coming from the account that's on my website?
 No.
 Well then it's not me.
 That should make everything simpler for you to read and for me to manage.
 I actually have a longer video coming up about this, about the actual specifics of hosting
 a server for all of this, because now I've got to.
 And so that will be coming somewhat soon, but expect all of this to happen somewhat
 soon.
 Not immediately, but a Fediverse presence and more open ways of communicating with me
 are a priority going forward.
 Plus, if you do really want an alternate video platform right now, there's always Patreon.
 Yep, money transition.
 Which is why I'm putting this at the end, since it feels kind of too self-promote-y to
 feel right putting it anywhere else.
 I do now have a Patreon and YouTube memberships page, where right now there are basically
 no perks and you should come in expecting that.
 I mean, eventually I would like to make something that actually delivers value and at that point
 I will do a proper announcement for this, but right now there are just ad-free videos
 on Patreon and shoutouts, kind of like this.
 Thanks to PT1997, look at them scroll across the bottom, since they're the only one right
 now I get to say them multiple times, PT1997, PT1997, I've had no clarification on the pronunciation.
 It's amazing to me that anyone finds doing that worth it for the videos that I make.
 So really, thank you, I appreciate it a lot.
 And if you're interested, you can find it on the website or in the description or in
 the YouTube websites on my main channel page if you would like to.
 There's also YouTube memberships, but just to be fully transparent, they take a bigger
 cut from me, so either I get less money or you pay more, Patreon is probably better unless
 you really don't want to leave the platform, but they are an option for you.
 And for those wondering, since this has kind of turned into a section about me again at
 the end of a video like last time, so that will stop happening once I have less things
 to catch you up on, that website, issacdowling.com, will not become some mess full of trackers
 that's really slow and a bunch of ads and things like that.
 Full transparency.
 I had considered adding ads to it with just the option to turn them off.
 I thought that might be a nice middle ground and maybe in the far future that would be
 something I would consider again.
 But at the moment that is just, and for the foreseeable future, that is just not something
 I'm interested in.
 Not only would it earn me very little and cause you more hassle, it would also cause
 me tons of hassle because I would have to deal with GDPR stuff, just makes everything
 much more complicated.
 I would like to keep it nice and clean.
 Same goes for trackers.
 There will be no Google Analytics on it and if I ever do add analytics, which I genuinely
 would like to at some point, they will be incredibly basic and I'll still have no GDPR
 stuff to worry about since I'm not interested in your personal data.
 All I really want is some old web style visitor counter at the bottom since I think that could
 be kind of cool.
 I do not want to touch personal data with a 10 foot pole.
 That would be a moral and legal nightmare for me.
 I don't want to touch it.
 I just want to know the number of visitors so that may eventually happen.
 If you have any input on any of this, please, please, please, feedback is vital in this.
 If you don't want to help me with the algorithm by getting me more engagement, by commenting
 about it, use the Discord server, email me, I have an email on the website.
 Any way you can get to me.
 If you have any ways you would like me to approach those things or just any notes on
 what I'm doing, now's the time for it since now things are kind of changing.
 I really hope you enjoyed.
 PT1997 you get to double dip because I mentioned you before and then this is the actual end
 of the video.
 I really, really appreciate it.
 Hopefully you've enjoyed and bye.
