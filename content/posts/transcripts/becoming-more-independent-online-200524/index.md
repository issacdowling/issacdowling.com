---
title: "Transcript: Becoming more independent online"
date: 2024-05-20T01:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---

 Too many modern websites are bloated, typical social media is on a downward trend, and email
 actually doesn't work like it used to because of consolidation. And I've been planning on
 joining less centralised social networks and fixing my website and email for a while now,
 but I don't just want to jump into one company's way of doing things, because what if they shut
 down or what if they suddenly change how things work? I want everything of mine to be standard
 and as portable as possible and to own as much of the platform as I possibly can.
 But I also want to be cheap. Which makes things more difficult, especially since
 I've got different requirements in that regard depending on the service that we're talking about.
 But the first thing we'll start with, since it's probably what you're most expecting,
 the Fediverse. Mastodon is by far the most well known piece of Fediverse software.
 So well known that some people, including me sometimes, just use it as a stand-in when they
 mean any of the other ones. We just say Mastodon in the same way that you might say you'd photoshop
 something when you actually just mean edit the image. And the reason that Mastodon can talk to
 all these other pieces of software is the same reason that your Gmail can talk to your friend's
 Outlook. It follows standards, specifically a standard called ActivityPub, which is an
 official standard for how social media should work. The problem is, even though it's really
 nice that it gives you choice, that just adds to the analysis paralysis. Do I want GoToSocial,
 Mastodon, Pleroma, Akkoma, PeerTube, PixelFed? There are a bunch of different things that
 don't actually necessarily do the same thing, but all use ActivityPub underneath so they can
 all talk to each other. The most obvious choice there, again, is Mastodon because,
 as mentioned before, it's the most well known. But it's also pretty well known for being kind
 of resource heavy, which isn't acceptable in my case because I'm going to be running it in the
 cloud because I'd rather not expose something on my home network directly to the internet.
 And that means I'm going to be working with 20 gigs of storage, 2 gigs of RAM, and one CPU core,
 which means I just can't use something that's so inefficient. Pleroma seems to be basically the
 closest thing to Mastodon except easier to run, and I was recommended a fork of that called Akkoma,
 which at first glance looks good, but I'm going to be honest, I didn't know much going into this,
 and I still don't really about Fediverse software and their different merits, so I was just going
 on what the repo looked like for the most part. However, before I put the effort into actually
 running it, because again, I'm going to be running it myself so I couldn't just find an instance and
 try it and then I would know if it's good, I decided to look at another category of Fediverse
 software, specifically things made for single user instances, ones where instead of having a
 whole community on them, I would just have an instance for myself and then I would connect to
 other servers, which is what I plan on doing. And two pieces of software that stood out to me were
 GoToSocial and Microblog.pub. GoToSocial seemed especially interesting since partially it's
 written in the language that I'm currently trying to learn, Go, but also it just seemed ridiculously
 resource efficient compared to anything else I'd been looking at. The only reason I didn't end up
 going with it is because of its self-admitted beta state and I kind of, I don't know enough
 to troubleshoot Fediverse things, and because there's no web UI, and even though I don't plan
 on using the web UI myself, I would like people who aren't part of the Fediverse to still have
 a link to go to if they just want to see my posts, kind of like you could with Twitter or
 anything else like that. So GoToSocial didn't seem like an option there, even if it's probably
 ideologically closer to what I want. So it's Akkoma that I went and set up. The install guide
 was fairly simple to follow, even if the compile times were a bit bad on the hardware of my VPS,
 and I misread the configuration docs a few times. But yeah, within around an hour I went from not
 to this. I've got a custom theme, I disabled seeing a federated timeline from the site, since
 although federation is still happening, my server will talk to other servers. You should only be
 using my web UI for quick glances at my profile, the point isn't to use it as your own instance.
 And importantly, since they're on by default, I disabled signups from the web UI. I can kind of
 see it making sense that they'd be on by default, since most instances of Akkoma won't be single
 user like mine, but also it seems like they should maybe be off by default for you to enable
 once the instance is fully ready. If I hadn't disabled this, anyone could just go to that
 website and sign up on my server. But besides that, I've had no issues. I can sign in fine
 through apps, I've tried Tuba on Linux and Moshidon on Android, both of which worked fine,
 and I was actually very impressed to see that they use OAuth rather than some weird API key thing,
 which I was just surprised given it's something you set up yourself, but it felt very fancy and
 nice. And I tested federation with someone in my Discord server and that seemed completely fine as
 well. I wouldn't say setting up my own instance was painless, but it was surprisingly not painful,
 it was the expected amount of pain. And I think that the main issue with it, like I mentioned
 in the intro, is that with the Fediverse there were just a lot of choices, and eventually I just
 went and picked one and it seems to have worked, but still, I gotta think in my head, what if I
 would have picked Go to Social? How much lighter would it have been? How much easier would it be
 to configure? What if there's some other piece of software that I've just not heard about?
 But eventually you just have to settle with something that works, and Akkoma works well
 for me. We're not done though, since although it's nice to have my own social media that's
 fancy and set up by me, I don't honestly expect to post too much but we'll see how that goes,
 I still need to fix my email and website. Though this is obviously not sponsored by Squarespace,
 I do think that having a website is important, it's just I want to be cheap, and I don't need
 the kind of things that you get from companies like that, like a fancy site builder and looking
 super modern, I just need something basic that I need to update, the once in a million years that
 I make a new blog post or post a transcript for a new video, and for that I think a static site
 generator would be perfectly adequate. With that I can design a whole site in just markdown,
 which is basically just text, I can modify a theme to match exactly what I need out of it,
 and then the static site generator will take that markdown and, following the rules of the theme,
 turn it into HTML that a browser can understand. Then I just need to find a way to publish that to
 the web, and I've got a really quick way to make new posts when I need it and modify things really
 simply and not need to mess with the HTML directly much, and the output from that is basically as
 fast as you can get since it's pretty much just HTML and CSS being served directly to you.
 I mean, that's so simple, maybe I could find someone to host it for free. Someone who'll host
 it? What happened to self-hosting it? Well, with something like social media, I really do require
 full control over that whole situation, and it requires a pretty small but still a non-zero
 amount of resources, so just a VPS or a Linux box in the cloud is the solution for that.
 But a simple website? The amount of resources required to run that is practically negligible,
 and the main priority here is that I control the domain. So yeah, I can use a free tier,
 and if I get kicked off it or I go beyond the capabilities of it, I could switch to someone
 else with a better free tier, or worst case scenario, I could just put it on a VPS. Websites
 are very simple, and there are lots of places that you can get to host them for free. In my
 case, I'm using pages, which there's GitHub pages, GitLab pages, CloudFlare pages, but they're all
 the same concept. You can point them at a Git repo of your site, and whenever it changes, they will
 build the site and publish it for you. Then I can just point my domain to that, and I've got a
 website. The actual static site generator I use is called Hugo, and it's the one I generally see
 most recommended nowadays, and the really cool part of using something like that and then pages
 to host it is that, well, actually anything could host it. I could use fancy magic cloud things like
 pages, I could use a regular VPS, I could use a Raspberry Pi at home, and if I want to, which I
 do so I have it public, you can just look at that Git repo that my site is built out of and you can
 see everything that's put together. Plus, it's more accessible, both in the typical sense of the
 word that I imagine, though I don't actually use one so I could be wrong, that simple just HTML is
 very very easy for a screen reader to use, and there are no GDPR issues, if you block JavaScript
 it's not going to break the site, basically anyone can access it and basically any connection will be
 able to load it super quickly. Plus, I compress all the images on the site very heavily so those
 shouldn't affect it too much. So with all of that in mind, although I definitely do see the point
 and the value for some people in a graphical site builder, the extra complexity and lack of
 portability for me doesn't make sense in this case. I have found a static site generator with pages
 super flexible and workable for me. And both lastly, and most simply for me to get set up,
 emails, which I think a lot of people overlook now since they just come free with most big tech
 signups, you know you get a Gmail and an Outlook and you just have those, but there are a lot of
 reasons that they sound ideal to self-host. A lot of email plans only come with single digit to low
 tens of digits of gigabytes worth of email storage. Meanwhile, if you're storing things locally,
 terabytes of mechanical storage can be had for less than a year's worth of that email service.
 Plus, there are the obvious privacy and potentially security, if you set it up really
 well, benefits of having everything go directly to you. The problem is, modern email isn't as basic
 as it should be. Rather than one person being able to go beep boop SMTP here you go mail server and
 the other person going beep boop IMAP mail server give me the emails all is good everything was
 received. There's a lot of stuff going on in the background as an attempt to fight spam and that
 kind of thing. IP addresses can have reputations for the kind of email that they send regardless
 of the actual content of the email going through them. So a spammer might have used a server first
 and then you join it, you send perfectly fine emails, but then Outlook might receive it and go
 I'm not even going to read it this is going straight to spam or potentially not even getting
 delivered at all because well it might be suspicious. I actually used Outlook as an
 example there because yeah I could use Gmail or Proton or Outlook and they all support custom
 domains so I could still have it look fancy and nice and stuff except I have sworn off Outlook.
 While using just their free tier, so not doing anything fancy, not configuring anything myself,
 they have sent a bunch of important email to spam. I don't think there have been any cases where it
 hasn't been delivered though I wouldn't know because I wouldn't have gotten it but there are
 lots of times where actually important things that I needed to see went to spam and everything
 in spam gets deleted after 10 days so there are probably things that I just never saw.
 Furthermore even though you'd think it might lighten the load on the mail server if it didn't
 have to check all the emails for spam I can't disable spam filtering plus there are just the
 other issues with Outlook web like the focused and other inboxes which had to turn back into a
 normal one and the ads and stuff but just in general uh Outlook particularly has been a bad
 time for me and then for the other email services well Google is kind of the exact opposite of being
 more independent online and Proton sounds pretty nice but also are relatively expensive compared
 to what I'm looking for since they offer quite a lot in their suite but I'm not interested I just
 want email. Ultimately no matter what platform you go with setting it up will be exactly the same
 Purelymail seems like a great choice if you just want email Zoho has a whole suite if you're
 interested but also I've heard meh things about them. Proton is probably a good choice if you want
 a whole suite of things and if you really really do want to self-host it yourself there are Docker
 images that make that as simple as it can be just keep in mind that IP reputation stuff and email
 delivering and receiving it can just get messy so this is the kind of thing where I'm going to
 entrust somebody else to handle that for me. All I had to do was pay some money point my
 domain to the email company servers set things up in an app and be done and if you're looking
 for some apps I'm currently using a K9 mail on Android and I would recommend Thunderbird on Linux
 if you're looking for something fully featured and Geary if you just want just email without
 much complex stuff going on. Ultimately besides the rest of it a huge huge part of why I prefer
 being more independent with my emails even if I'm still relying on another company to actually run
 the servers is that portability if my account were to be randomly automatically flagged as a bot if
 the company were to go bust no matter what happens I still control the domain as much as you can
 and so I can just move I don't have to worry about what company I'm using and whether they will stay
 the way they are I just need to think about well what's cheapest what matches the features I need
 the most like that kind of thing. The goal as with social media and as with the site is to follow
 standards and just have fun if even if you think everything else I've said has been pointless so
 far that's my catch-all that makes this worth it for me it's just kind of more interesting to do
 things this way and think about the infrastructure that makes the things that I use work. If you want
 to ask questions or talk about technology you can do it in the discord server below. Huge thanks to
 Ducky! and pt1997 who subscribed on patreon and are going by on the bottom of the screen you can
 do that too if you'd like to if not subscribe if you think it's worth it and bye I'll see you next week
