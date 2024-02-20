---
title: "The importance of FOSS"
date: 2024-02-09T19:00:00+01:00
authors: ["Issac Dowling"]
categories: ["Trancript"]
draft: false
showTableOfContents: false
---

﻿So much tech has little problems that seem like they should be easily solvable
or were only even introduced for ridiculous reasons.
Yet the developer doesn't seem to care, or maybe their company doesn't let them care,
or maybe it's an issue that you think you could solve,
but you don't have access to the code.
You get the app, but not the right to modify it.
Free and open source software, or FOSS, or FLOSS,
free specifically as in Libre open source software,
does mean that you, you, have the exact same right as the developers to modify the code,
at least for yourself.
And for non-developers, that means even if you can't program,
if you know somebody who can and they also like the app,
you can just ask them to make something.
And if they want to, they will.
And if they don't want to, you shouldn't harass them.
FOSS softwares are so generally designed to be user-first,
where if you're Microsoft, you might look at Windows and say,
I could make it easier to switch away from Edge,
but then nobody would
use Edge.
May as well not bother.
You've got an interest in making things not the best for the user,
so they're better for you.
But if you're just making an app because you want to use the app,
or you like making apps,
why not make it the best it can be?
So I wanted to make a video explaining why,
beyond the Stallman enthusiasts and I use Arch by the ways,
the freedom to use your hardware and software as you wish
is extremely important and can help you a lot personally.
When a big company decides to
remove a feature or change something you don't like,
the reaction doesn't always have to be,
oh, what am I going to do?
It's, oh, what am I going to do?
And then you find something to do.
Probably the easiest to explain example of this taking-things-into-your-own-hands attitude
is Home Assistant,
where someone finally said,
no, if you smart home brands don't want to work together,
I'll make you work together.
And if you're tired of controlling them
with the ever-listening, ever-mediocre voice assistants that are proprietary,
well, there's Rhasspy, Home Assistant Assist,
which is the one you should probably actually be using at this point,
and even the one I do, Bloob.
I mean, I can just say, in a fully open-source stack,
Blueberry, make the door light red and the bedside light blue,
and it'll do it. That's really cool.
Plus, instead of Philips Hue or any other proprietary lighting system,
which doesn't necessarily force you into keeping with their ecosystem,
but does involve such a high monetary investment
that it's probably worth just sticking to them
if you want everything to be the same and everything to feel cohesive,
I can light stuff by just soldering together some LEDs and a microcontroller,
put in WLED on it, and boom,
I've got something that can work standalone within other smart home ecosystems,
it's all open, and I can customize it to be exactly how I'd like.
Philips Hue probably wasn't the best example,
because as far as I know, their main issue is price.
But I haven't actually seen older Philips Hue bulbs
get disabled.
So the problem with closed-source smart home things
is the devices that do get axed.
Philips Hue is the exception to the rule
that any device with internet-connected functionality
will eventually lose it,
and there's no legal recourse for customers
that have just had their devices suddenly disabled in some way.
If instead everything is open
and all of the servery things are ran on your own devices,
what exactly is there to take away?
Till the traces on its PCB
go black or 2.4 GHz WiFi stops existing,
those WLED lights will keep working exactly as they always have.
In stark contrast to multi-billion or multi-trillion dollar companies
being able to deprecate this and change that
even if I don't want it changed,
if WLED were to make a change that I didn't like,
I can just roll back.
So it is with every open project,
and so it should be with everything you buy.
And I realize maybe I went on for a bit too long
about smart home stuff in
particular,
but at least it's a very good example,
and we're about to see more.
Recently, my Samsung phone updated to One UI 6,
and I think it's worse.
I mean, the new fonts are nice,
even if I didn't have a problem with the old ones,
they copied the iPhone, again,
but more customization is a good thing, so fair enough,
but they changed the notification quick access buttons.
They're now visually more cluttered,
and, in my opinion, less reasonably organized.
Can I do anything about that?
Nope.
There's no option in the settings to go back to the old way,
it's just stuck how it is.
And that's really frustrating,
but not frustrating enough to, probably,
convince people to switch phones.
So all we're really teaching companies
by accepting this kind of thing
is that, well, if they mess with our things
a little bit at a time,
we're probably going to do nothing about it,
and it's just seen as okay to take away the choice
and take away customization,
for a company to decide this is how things are now,
because we always just stick with it.
Contrast that to the Linux way of doing things,
and yes, Android is technically open source at its core,
and even Linux at the core,
but it's really, really not the same,
and these Samsung and Google ad ditions
definitely are not open source.
The Linux way of doing things is that
an update came out, people didn't like the look of it,
so people took the old one and kept it going.
That's it. That's all.
There's no more complicated,
"we petitioned for the developer
to make it the old way",
or I had to file a bug report or an issue
and try and ask them to change it,
they just took the old one,
because it was within their rights,
because it was open source software,
and they kept on going.
That's obviously the switch between Gnome 2 and Gnome 3
and people carrying on Gnome 2 as Mate.
Nobody's stopping you.
So if you have a workflow,
and enough other people have a workflow,
that can just carry on for as long as you like it,
even if other projects decide to change things.
Nothing is going to just randomly brick itself
and stop working, because "that's not the way we do things anymore".
Unlike the Diamond Northwest bus app.
I realise this means nothing
to anyone who isn't in Manchester,
maybe you've experienced something similar elsewhere.
We had the transition recently-ish
to the Bee Network.
All of our buses are yellow now,
updated with USB-C and screens
and they announce the next stop
and all of that fancy new thing.
Electric buses. Woo! That's a good thing.
The problem is somewhere
during that transition,
the Diamond Northwest bus app
no longer tracks a bunch of buses
live locations anymore.
Which is really frustrating
if you want to get those buses
because you don't know where they are
and timetables are never accurate
and especially if it's a once per hour thing
I'm ranting about buses at this point.
Luckily, that's not a problem
because the government has the open bus data service.
All bus companies have to publish
the buses live locations
just as an API that we can access.
And someone built an open source website
called bustimes.org around that
and it's excellent.
It's the best resource in the UK for tracking buses.
It goes far more in depth.
People take pictures of these buses.
You can see the license plate of the bus
that's about to come to you
and I realize I'm getting giddy over buses
but the point is
this thing got ruined by the companies
that manage it
because there is maybe not literally open source
but not vendor specific
access to this data
and to these tools
someone just made a solution
that's better because they could.
This is excellent and exactly the kind of
ethos that open
software inspires.
So, a huge shout out to Kieran Mather
and the later maintainer Joshua Goodwin
for that. I just feel like
if I'm crediting the wrong people
please, please, please tell me because I really want to credit them.
This is just amazing.
On to the next thing. Although we've not been looking at
typical app apps so far
those are probably the most relevant for regular people.
I mean, pay your respects to
VLC, OBS, Firefox,
Blender, LibreOffice,
most emulators, Audacity
or the forks of it now,
Linux even as a whole.
Are you saying you have none of those on your computer?
If not, why?
Not only are those all good apps
they're often actually the standards.
How often do you see VLC on someone's computer
because, well, it's just the best
and Blender, Blender is an actual standard
that real people use in real jobs
for 3D modeling. People aren't using those
because they'd like an open version
or something else. They're using them because
they're the best thing.
And that's not the case for everything.
There's Photoshop and then there's GIMP
but GIMP isn't trying to be Photoshop.
It's okay for one thing to
not be another thing.
It's okay that Classicube isn't Minecraft.
They're not trying to be.
It's okay that OpenArena isn't going to be the next
Modern Warfare. It's not trying to be.
Linux is unapologetically
not Windows and that's okay.
For lots of these open source apps
they are not quite the same as the
open source version, especially
video editing. Kdenlive is just not
resolved at all.
But it doesn't have to be because for many people
that's good enough and as separate
projects they still work well.
You know what all of those apps are?
Good, no nonsense, free
and just really useful.
So open source obviously
isn't perfect, what is?
But it and the
open mindset are probably the best
we've got even if they don't fit
every project perfectly.
And there's so much good stuff
that if you're willing to stick with me for a minute
I want to recommend you a few things.
Not everything I use, not even close,
but a few of the standouts
that seem particularly applicable to my
audience. First,
nothing to do with my audience, breezy weather
on Android. It just
looks incredible and there's
no nonsense, no rubbish to it.
It works really well. All I really
need to show you is this.
It looks like that and it works
well. Go and try it.
Next is notify.sh
or ntfy.sh
If you like
hacking things together or building
kind of awkward solutions and you
need notifications, notify.sh
It's just, it's excellent.
It's probably not for everyone but it's
super simple to get a notification.
There are clients for computers and phones
and you could probably make one for basically
anything. It's just really really
useful even if this probably isn't relevant
to everyone. Next, Joplin.
Having a potentially proprietary
notes solution if you rely on them a lot
is a terrible idea.
If that company does something you don't like
or they start charging or anything like
that, you're stuck with them unless you want to
go through a really awkward process of exploiting.
That's obviously not the case with
every notes thing and obviously you should
look at what's right for you. But with
Joplin, everything is marked down. There
are great plugins. It works really well across
platform. There are sync features. It's
customizable. Joplin is just
excellent and it's something I think you should
look into if you're currently using
a pretty basic notes solution
and would like something to replace that
and isn't proprietary.
And finally, since I've got one last thing
to talk to you about after this, so I
want to keep this section short, the
Fossify app suite. If you're an
open source enthusiast and you're
using Android, you're probably using
at least one of the simple mobile tools
apps. And that's because they're really nice.
They were simple tools for your
mobile device. They were open source. They just
worked well. They were recently
bought out and have kind of been
tarnished in the eyes of the open source
community. And Fossify has come in,
forked them, and kind of polished
them up a little bit and republished them.
Those are the ones you should probably be
looking at if you're currently using simple
mobile tools. And if you're not, and you need
a calendar or contacts app,
phone app, anything like that,
and you're currently using something proprietary,
maybe just give them a try.
Do you actually need a proprietary solution
for those? Probably not.
Maybe you're using Google's fancy
pixel call screening. Then you'll
need one. Maybe there's some magic thing about
your calendar app that's amazing.
But if it's not, you may as well give it a try
since I think you might like it. You could be
in a position, if you don't think about this often,
where lots of the apps you're using
are proprietary and there's no good reason
for it. So hopefully this video
has prompted you to kind of think
about that and maybe look at some alternatives.
And I've got one last thing to talk to you
about, and it's not related to the
concept of this video at
all. It's for long-term viewers, so
bye bye.
If you were just here for the open source stuff.
I've been gone for a while.
So that's because
I've had college things to do, and
beyond that, I've just kind of had
stuff to do. I've been very, very, very
tired, and
not very motivated
because having tons of stressful
things to do brought my
motivation down, but I still
had lots of work to do, and so I didn't
see this as an escape from
the boring things. I saw it as
something that
will take my very, very finite
energy and make
it even lower.
But recently, my motivation
with college and things like that
got low enough that
kind of things started to go back up
again, instead of having
this be an extension
of things to do.
I was like, if I don't do this, I'm just
I'm not doing the
things that I love anymore.
If I'm not doing this,
then I'm missing out on something huge
that I could be doing. I really enjoy
making videos,
and even
if I wasn't making the videos,
just the research involved in them makes me
find interesting things to talk about
that I just really want to know about.
So these are really selfishly beneficial
as well as hopefully you like them.
So, I'm
back, I think.
You should expect me to be fully, fully
back by March, and regular
things hopefully by the
mid to end of February.
I really appreciate
if you've been a long-term viewer
or even someone recently who's just
been like, I want more videos.
I see you, and I appreciate it
a lot since this is one of my favourite things
to do. I've been
skipping out on it, so thanks for
sticking with me if you have for the last
three or four months.
But,
I'm back. Let's do this.
Hopefully you've enjoyed,
hopefully you're excited to see more
of me over the
coming months and getting back
into things and making things better.
I want to continue videos as they were
in the past and
make those better step by step.
But I also want to get back to bigger things.
Half an hour long videos that are edited
really well and shot in
artsy ways just because I feel
like it. I am
creatively pent up
and I'm ready to
make videos again. Thank you
for watching, thanks for
sticking with this, and
bye.