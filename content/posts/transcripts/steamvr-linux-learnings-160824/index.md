---
title: "Transcript: What I've learned from using SteamVR on Linux"
date: 2024-08-16T01:33:31+01:00
authors: ["Issac Dowling"]
categories: ["Transcript"]
draft: false
showTableOfContents: false
---
I have quite a few videos about wacky VR setups, including using the Quest on Linux or the
Rift dev kit with Kinect and playing Beat Saber on it with hand tracking. The problem
is, even if I wanted to keep making those, I don't have a standalone headset anymore.
So why not take advantage of that and just make something about the general Linux VR
experience? Obviously, sometimes my particular headset will be relevant, but whether you're
using a Vive Pro, an Index or ALVR, we're all using SteamVR for Linux underneath, so
a lot of this should still be applicable. I plan on covering the interesting personal
bits and the why of my setup in the future, but this is mainly about the Linux experience,
not the hardware I experience it through. So I'll just say I do have a Vive Pro 2, but
for now that's reserved exclusively for Windows use, because it turns out the community driver
that's been made for it just doesn't work for me. Luckily, part of getting a very good
deal on the Vive Pro 2 setup was by getting the controllers and base stations through
a cheap Vive, like, full kit that included a full original Vive with crusty, dusty screens.
So no one wanted that headset, it just happened they were selling the full kit, so I got the
full kit and just didn't use the headset. However, I keep it in my old Pico 4 box for
storage, because, you know, reusing and stuff, obviously I don't still have a Pico 4. I just
took that headset apart, cleaned the screens, and now I have a fully working Vive, which
means that I can try things on Linux through that. As for the computer hardware, both what
you would need and what I have, I've got a Ryzen 7000 CPU and an RDNA 2 GPU, so modern
mid-range. But it's worth saying that a base level VR experience has not been a tough task
for basically any computer that can run any kind of modern game at all for a long time.
Like when this first iteration of modern VR headsets came out, there was a lot of emphasis
on needing a beefy GPU, because it's, you know, it's 3D, two screens, and you need really
low latency and really high frame rates. Um, you know, it's really tough to do. But if
you actually think about it in modern terms, the HTC Vive has a resolution of 2160x1200
running at 90Hz, so just above 1080p at 90Hz with typically not particularly graphically
demanding games. And thanks to things like single pass stereo, a GPU is probably actually
working about as hard as it would to drive a 720p screen at 90Hz when driving a VR headset.
So you shouldn't have to worry too much. Basically, as long as it's supported by modern Linux
things, you probably won't have too many issues driving at least the lowest tier of VR games,
especially if you're using one of these older headsets with the lower resolutions. Laptop
 users beware though, since things get more complicated here. I'm not going to blame Nvidia,
 despite there being an Nvidia GPU in this laptop, because honestly, there are many reasons
 that this could be happening. SteamVR could just be feeling quirky today. It could be
 just multiple GPUs, you know, the fact that laptops with an Nvidia GPU will also always
 have a GPU in their CPU, so I've got Intel and Nvidia. Or maybe it could just be the
 fact that I'm using a USB-C to HDMI adapter, because there's not a HDMI port on this laptop.
 There could be many reasons that this is going wrong. However, people have had success with
 VR headsets on a Surface Book on Windows. So regardless of what the problem is, it's
 unique to Linux. Steam did pick up the headset, which makes sense since it just plugs in by
 USB, and you know that because in the top right, Steam does the little icon that suggests
 you open SteamVR, but it just never fully initialised SteamVR when I tried to open it.
 And that applies both to just regularly launching SteamVR and letting it try to do its thing,
 or specifically launching everything with prime run to say, only use the Nvidia GPU,
 the Intel one doesn't even exist. For the most part, it does seem like Nvidia-related
 issues have been solved, be it Wayland or VR, ExplicitSync, anything like that. But
 it's also not far-fetched to imagine that this is just some weird graphics driver nonsense.
 To get things actually up and running, even Flatpak Steam will do you just fine. Did I
 have to modify anything outside of Steam? Nope, it straight away just picked up the
 headset within Steam, no permissions changes or anything, you're just off and it works.
 Do you even need to use Steam at all? No, there's Monado, which I don't use, and
 I don't expect you to use, so it won't be the subject of this video, but it's
 a fully open-source SteamVR alternative, so it's the OpenXR runtime that stands between
 your VR software and VR hardware. It's missing quite a few features, which is why I don't
 use it, but I'm sure there are quite a few people who don't need those and just love
 using Monado because it's so just nice and free and open source, and eventually I would
 like to join them, just not yet. Back to proprietary land though, there is a big difference between
 Flatpak Steam and not Flatpak Steam, and it's to do with, as you'd probably guess, the
 difference in sandboxing. A lot of you will probably only ever play VR things or run VR
 things from within Steam, in which case you'll have no problems with the Flatpak. But if
 you want to run outside software, like Vivecraft, a VR mod for Minecraft, if you're running
 SteamVR in a sandbox, that software is not gonna be able to talk to SteamVR, so it's
 not gonna work. You can get around that by, if it's provided as an AppImage, you can
 extract the AppImage, move it to a location that the Flatpak Steam has access to, and
 enter a shell within that Flatpak and run it there. I've done that, and that's how
 I used to play Minecraft, well, I didn't play it much, it's not actually that compelling
 a VR game, but that's how I tried Vivecraft. But that sandboxing is still a problem for
 me, even if normally I'm fine jumping through hoops, because already VR software is pretty
 scarce, then we've got native Linux VR software, which is like a tiny tiny fraction of what's
 available on Windows natively, and then you've got what's been packaged as an AppImage so
 you don't have to worry about dependency hell and being able to bring that into a Flatpak.
 I honestly know of nothing other than Vivecraft that would work in this way, but it's something
 to maybe look into, and luckily, if you're just looking to play Windows games, you can
 actually just add them as a non-Steam game to Steam, and they should be fine. Probably
 the biggest group of people that this is gonna affect negatively are game developers, because
 what, you'd probably struggle to put Godot into the Steam Flatpak sandbox, let alone
 Unity or Unreal, and it wouldn't really be feasible to build your game and add it as
 a non-Steam game every time you want to try a build, so yeah. I'm actually considering,
 on a development-related note, as we record it, we are a few hours away from the start
 of the GMTK Game Jam, and I'm still not sure whether to participate in it, but maybe that
 will be the next video you see off me if I do decide to join it. Although I mentioned
 this in my previous ALVR video, you'll have only seen it if you were there specifically
 for ALVR, so it's worth mentioning here as well. All y'all AMD users will probably be
 stuck with some pretty bad stuttering by default, and that's due to some power profile weirdness.
 Luckily, all you need to do to fix it is download CoreCtrl, or any other GPU overclocking,
 though we won't be overclocking software for AMD on Linux, I use CoreCtrl just because
 I don't want to have to think about it, make a profile that automatically starts when it
 sees the process "vrmonitor" and make it set your GPU to the virtual reality power profile.
 That should fix things stuttering solved. At least, if you apply a little bit of common
 sense on top, which is, you know, if you're still running a game that's just too difficult
 for your GPU, it's just too difficult for your GPU, that's not going to stop the stuttering.
 But come on, let's get to the thing that really matters. Linux users love to talk about speeds
 and feeds and specs and whatever, but the actual important thing is the games that you
 can play. And it's kind of easy to gloss over now that all of these, all of the most
 popular Linux gaming distros that were tailored around gaming to make things as easy as possible,
 as workable as possible and compatible as possible, you still actually can't play some
 of the most popular Steam games on them, and the same goes for VR. Now, my actual opinion
 on this, when not exaggerating and complaining about, you know, like, you still can't play
 Siege on Linux or whatever, is that there are so many good games that I'm not going
 to miss any that don't work on Linux, especially when I wasn't going to be playing any with
 kernel-level anticheat anyway, because I just don't like it. So I don't view it as a huge
 problem, but because why would it be any different? It does still apply that lots of games just
 won't work at all. Some might even work at first, you might buy them in a state that
 they work in, and then they'll get an update later, like Pavlov with version 29, I think.
 Pavlov just stopped working, but we'll get to that later if you know. However, luck has
 generally been on my side. I don't know whether that's to do with the fact that maybe more
 VR games will be made by smaller developers just using Unity or Unreal and compatibility
 issues with those engines in particular can be worked on and it helps tons of games. I'm
 actually not sure why VR games tend to work better through Proton than regular ones, at
 least in my experience, but that tends to be the case. And despite the fact that Linux
 is still obviously a small market, the fact that Linux as a platform for gaming is constantly
 growing means more and more we are seeing developers care about it and perhaps games
 that didn't work or used to work and now don't work, those games are now getting patched
 to work again, as we saw with Pavlov. Pavlov works again in Linux now. Just some general
 good news since it's probably the game I have the most hours in, even though it probably
 has the least depth, Saber-Beaters will be happy to know that you can slice blocks just
 fine and there are even options for native mod managers, though you probably could still
 run a non-native one through Wine if you really wanted to. Though, as I'm obliged to tell
 you, I'm a tiling window manager user. Before that I used Gnome and before that I used KDE.
 If you're on X and using any of those, you're just ready to rock, everything will be fine.
 But if you're on Wayland, things actually aren't that bad, have higher expectations.
 For the tiling window manager crowd, anyone using WL roots, so that will be Sway and Hyprland
 being the most relevant there, will be fine and KDE also has been fine for a long time.
 And the thing that they're fine about is supporting DRM leasing. When talking about Linux, at
 least normally, when you refer to DRM, we're not referring to digital rights management
 or the taking away of your digital rights when it comes to the content that you pay
 for. We're talking about the direct rendering manager, which means when rendering a VR application,
 instead of rendering your desktop environment and then the VR app on top of that and it
 being managed by the desktop environment and then that being sent to your headset,
 SteamVR can just say, actually I want to directly render to the display of the headset
 without worrying about any in-betweens and that helps fix issues like your desktop being
 visible on the headset and just generally latency and performance improvements because
 it's just simpler. However, you do have to actually implement support for it and this
 is generally uncontroversial with everyone except Gnome. It seems like everyone else
 just implemented something that worked and left it at that, where Gnome implemented nothing
 and spent ages talking about how amazing it would be if we had a perfect solution involving
 permissions and portals and the modern Linux way of doing things and I also admit I would
 prefer things to be that way. It's just that no one else is on board with it, so while
 everyone else has had working VR for ages, Gnome has had nothing and they still technically
 don't. However, with the release of Gnome 47 soon, the changes to make it like every
 other desktop should be merged now, so you should be all good even if you're on Wayland,
 even if you're using Gnome. Huh. I think I just made it through a whole VR video without
 an extended cut of me playing Beat Saber. I know this isn't an all-inclusive video,
 these are just the things that I have experienced and a lot of my time Linux VRing has been
 with ALVR, so maybe I don't have, maybe I shouldn't be talking about all of this without
 more experience. Also, I have no idea how I didn't mention it because it was literally
 in my notes right there. Screen mirroring is also another awkward point for Linux VR
 things, since I've had it work like once for me and I think it's an X vs Wayland thing,
 I'm not sure, but if you're used to virtual desktops and stuff in SteamVR, you're probably
 going to have a bad time with that, but there are native Linux alternatives to kind of take
 over what SteamVR is doing until it works there. But I hope that at least some of you
 have found this helpful if you're considering getting into VR. I know for me at the end
 of a video, the only thing I'm considering doing is chatting at my supporters. So a huge
 thanks to Pieteek, Ducky!, pt1997, and Russell Willis, I really appreciate it. Hopefully
 you've enjoyed, subscribe if you like to, and I'll see you next week, maybe with some
 updates on the GMTK Game Jam, if I do it.
