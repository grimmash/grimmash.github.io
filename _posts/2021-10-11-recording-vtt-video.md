---
layout: post
title: Recording VTT Video
date: 2021-10-11 20:52
author: grimmash@gmail.com
comments: true
categories: [ttrp, video, production, obs, foundry, discord]
---

This post is an overview of how I record and cut the videos I post to YouTube.  I hope to give some insight on one possible way to record and produce session videos here.  A huge caveat up front: These are the tools *I* use and the way *I* do things.  I am not a professional.  There are other options for every tool.  There are other, and probably better, ways to do all of this.  The methods below are where I have ended up after about a year of dedicated attempts to record and share my sessions and some other videos.  Whatever fits your budget or preference is just as good!  You can find my videos [on my channel](https://www.youtube.com/channel/UCWr9F5MlrUzyicKo0xuWeew) and decide for yourself if I am any good at all of this!

So let's go!  I will give lists of the software and hardware I use.  Then I'll give an overview of recording and producing a session.  This is an overview, not a step by step; there are too many permutations of software to go step by step.  That said I will try to give specifics where I think it matters or is useful.



---
<h2>Tools Used</h2>

**Software Tools**
- [Foundry](https://foundryvtt.com/) ($50 USD)
- [OBS](https://obsproject.com/) (Free)
- [Discord](https://discord.com/) (Free/Paid for Nitro)
- [VoiceMod](https://www.voicemod.net/) (Free, but I got a $25 lifetime subscription for all filters)
- [DaVinci Resolve](https://www.blackmagicdesign.com/products/davinciresolve/) (Free Version)
- Browsers of choice
- Recordkeeping Software of Choice

**Hardware**
- Windows 10 PC, custom built:
  - AMD Ryzen 3800x
  - 32gb Ram
  - NVidia 1080 Ti
  - 1tb NVME drive for recording
  - Normal HDD for editing
- Blue Yeti (audio)
- Various Webcams (video)
- Four monitors:
  - 1x 3440x1440 Ultrawide (DM Screen)
  - 3x 1920x1080 displays
---
<h2>Software Overview</h2>

<h3>Foundry</h3>

I use Foundry as my virtual tabletop.  This is down to personal preference.  I think Foundry is currently the best VTT on the market, but all of my methods should work equally well for any other VTT as long as it appears as a window on your PC.

I self-host, so all my Foundry content is on my PC and I open the hosting link up for game sessions.  You can also use Forge or other hosting solutions to have a third party host your content.  The advantage to this would be allowing players to always have access to the game world and tools in-game.  The downside is paying for hosting costs.

**The Camera Account/Player**

I like having a second VTT open, set to player vision, and I record that instead of my DM instance of Foundry.  This is my "camera".  In Foundry, and I imagine other VTTs, you can create users or players that share vision with PCs.  In Foundry this is achieved as follows:
- Create a Player.  Not a character, a **player** account.  For bonus points give it a cool name that fits the game, so if your cursor goes flying around it has some lore friendly name.  In my Curse of Strahd game, it is called "Raven".
- Give that Player "Observer" roles for all other PCs and NPCs that have vision the actual players would be aware of.
- Using the Invitation Link for a locally hosted game (or remote if you are using hosted Foundry), open a browser and log in as that "camera" player
- You now have an invisible cameraman!

When I load this account in in my camera browser, instead of seeing the DM view, it only sees what the players can also see!  


**Other Options:**
- Roll20
- Owlbear Rodeo
- Fantasy Ground
- Tabletop Simulator
- TaleSpire

<h3>OBS</h3>

I use this to record all my audio and video.  If it is on my channel, I recorded it with OBS.  I use multitrack recording, which is awesome but does require you to set up individual inputs for each recording, and then balance it all in post production.

<h3>Discord</h3>

Used for voice chat and for streaming in a pinch if a player loses a connection to my VTT.  I assume most readers know what Discord is.  You could also use Zoom or Skype or really anything that works for your group.

<h3>VoiceMod</h3>

VoiceMod is a tool that lets you modify microphone input through voice filters like "Devil" or "Child" or other similar things.  In my Tomb of Annihilation games you can hear this being used to voice Withers and Belchorzh.  There are many other options, I use VoiceMod since I got the full license on sale for about $25 USD.

<h3>DaVinci Resolve</h3>

This is a video production suite.  It is comparable to something like Adobe Premier or Apple Final Cut.  I do all my post processing of video and audio in Resolve.  I used to use CyberLink PowerDirector.  DaVinci Resolve has a free version that has ridiculous tools at no cost, and that price is right for me.  Any option you choose will have a learning curve.  Most have plenty of YouTube videos that will help you learn the ropes.

<h3>Browsers</h3>

Not much to say here, except that I usually have a few browsers up to reference rules, reference character sheets (DnD Beyond and HeroLab Online), and other similar things like that.

<h3>Record Keeping</h3>

Another not terribly interesting issue.  I use Excel, OneNote, Google Docs and handwritten notebooks.

---
<h2>Hardware Highlights</h2>

<h3>What should you spend actual money on?</h3>

I think this is a super important thing to touch on from the start.  Video and audio production can eat money.  **Don't buy anything, start with what you have.**  So you still want to spend money?  What really matters for the end product you produce?  I would argue the priority list for buying non-entry level gear is:
- A decent microphone.
- A decent set of monitor/reference headphones.
- **If** you want to do video, a DSLR camera or something similar.  
- **If** you do video AND need a greenscreen, a *good* greenscreen that fits your recording space.

A good mic makes you sound way better.  A good set of headphones will let you actually be able to hear the difference.  You can get some great "hobby grade" mics and headphones for about $100 to $150 each.  But keep in mind, most people are watching on phones and listening on earbuds. **If you are new to this, what you should really do is use what you already have and find out what will make you feel or work better at producing your content, at a price you are comfortable paying.**

<h3>PC Notes</h3>

I only point out my general PC hardware spec to provide a bit of a benchmark.   My PC can run all of the programs here at a very satisfactory level.  Some general thoughts:
- I would recommend when recording with OBS to write to an SSD or NVME drive.  You also want to minimize extra applications open while recording and rendering in your editing software to ensure you have enough CPU and RAM headroom for a smooth recording and rendering.  
- Some video production tools really prefer you to have the data on one drive and the render file on another.  Make sure you look at that requirement and others before paying money or doing a ton of editing work!

<h3>Monitor Notes</h3>

I run 4 monitors because I had them already.  You don't need that many.  None of them are bleeding edge high performance monitors.  I have collected them over a decade of being a nerd.  I just like having lots of screen real estate.  If you are using OBS you can also capture windows instead of screens, which is a powerful tool if you can't run a monitor dedicated to your "camera", which I will detail later.  

<h3>Microphone Notes</h3>

You don't need a great mic to record usable audio.  A better mic *will* sound better, but most "better" mics will *also* require more effort to reduce background noise.  Go figure, good mics pick up more sound.  You can hear my key clicks and ambient noise all the time in my videos.  If you *do* want a fancy mic, my recommendation would be to find a mic that picks up well from a few feet away, or use a headset with a decent mic.  If you have to lean in to the mic all the time, it may get physically awkward to run virtual sessions.  And it will look weird if you do video recording of yourself.  If you have a gaming headset, start with that and then decide if you want or need to spend more money and invite more challenges to solve.  

For the record, I use a Blue Yeti on the Yeti Caster arm.  A decent package, but I may try other mics and arms at some point.

<h3>Webcam Notes</h3>

I briefly tried running with a camera, and a greenscreen.  I stopped because cameras, greenscreens and chroma keying and all that is a place where you really get what you pay for.  You also need space for a greenscreen, mounted or mobile.  Given I record in the family playroom at night, the greenscreen was just too much effort.  

Regarding cameras, I used a Logitech C920 Pro to start and I hated it.  It was too wide angle and I could never get the color to work well, and I found it fiddly to adjust anything.  I switched to a Razer Kiyo, and have found it much better for this specific use case, with a bit less fiddling about.  Any camera can be adjusted wither with the camera software or in OBS directly.  OBS also allows chroma keying directly within OBS, and you can see the results live.  

Also, a dirty secret, most YouTubers that put their faces on screen are NOT using webcams.  You can go deep down this rabbit hole, but if you already have a webcam, don't spend more money on *another* webcam hoping it will up your video fidelity game in a serious way.  It probably won't make much difference.  If you think mics are expensive, just start looking at digital cameras!

That said, if you decide to record your video, spend some time watching your behavior:  
- I am constantly leaning, moving, etc, and you can see it in a few videos.  It is super distracting!   
- I also like to eat/drink while playing.  That looks terrible on the camera!  
- If you use a lot of gestures and no camera, or don't post the camera video, think of how to convey that physical information some other way.  No camera means no one can see your gestures or expressions.

---
<h2>A Day in Recording and Production</h2>

<h3>Launch and Position All the Things!</h3>

Now for the nuts and bolts of how I do this.  My first steps are to fire everything up:
- **Main Monitor:** Foundry gets put fullscreen on my main monitor.
- **Monitor Two:** Discord and either OBS or VoiceMod, depends on what I feel like needs the most attention.
- **Monitor Three:** All my supporting browser and note taking apps.
- **Monitor Four:** Fullscreen Foundry in a browser for my camera account.

They key thing is not opening windows once the game starts.  This can cause the full screen "camera" account to hiccup for a second.  I solve this by having all my support browsers and windows on another screen all ready to go.  The other reason I give the "camera" a dedicated screen is so I can always see if I am recording the action correctly.  You can see plenty of cases in my videos where I fail to do this well.  It also lets me see what the players are doing.

<h3>Set Up Audio and Video</h3>

I do some basic checks every session once all my tools are running:
- Launch **Discord**, **OBS**, **VoiceMod** and **Foundry**
- Check **VoiceMod** inputs and outputs.  In my case:
  - Input is my Microphone
  - Output is my headset
- Check **Discord** inputs and outputs:
    - Input is VoiceMod Virtual Audio Device (this makes sure either way I run the audio (voice on or off) it goes to Discord)
    - Output is my headset
- Check **Foundry** sound:
  - Sound is muted in the camera account
  - Sound is running in the DM account
  - Turn on some background music or something
- Check **OBS** sound devices:
  - At this point I already have separate sound devices for my mic, VoiceMod, desktop, headset, etc...  You will need to set this up ahead of time.  Google tutorials on adding devices to OBS.
  - Make sure multitrack recording is ON
    - Settings > Output
      - Output Mode: Advanced
    - Under Recording Tab:
      - Recording Format: I use .mkv.  Make sure you use a multitrack format (that your video production software can use!) if you want multitrack audio
      - Check how many tracks you want to be in the output
  - Now back on the main screen, on the side of each audio track is a gear.  Open any gear and go to "Advanced Audio Properties"
  - Assign your audio devices to tracks in the output.
  - Make sure these are enable in the OBS steps above!
- Set up **OBS** video
  - I just record the one screen, you can add a device based on your needs (screen, window, etc)
  - You can set up multiple screens or inputs, resize them, move them around, and use chroma keys if you have a green screen.  This is a topic all by itself, so search something like "how to set up a greenscreen in OBS" or "how to use an overlay in OBS".
- **TEST EVERYTHING:** Once a player is in Discord do a quick 10 second recording to make sure everything works.  Toggle VoiceMod on and off, play some background music, have a player say something, etc.  Just test all you audio and video.  Once you get used to this, your players may not even realize you are doing it as part of the pre-session banter!
- If you are really concerned, open that short clip in you video editing software and make sure it all works.  All the audio tracks are there, you are recording the right screen/window, etc...

This list looks really long.  Once you get things set up though, OBS remembers your settings, and you can even save multiple Scenes to switch settings quickly!  In practice doing all this takes about 5 minutes, and that is when something is going wrong.

<h3>Play the Game</h3>

At this point, all you need to do to start recording your game is press the "Start Recording" button and you are good to go.  Remember to check in on your camera account/window/screen frequently so you can keep it focused on the action!

The main consideration here is if you want to record one big video, or split the recordings up.  I have done both, and both have positives and negatives.  Dealer's choice!

**Emergency Streaming:** If a player has connection issues, you can use the camera account to stream through your streaming platform of choice!  For Discord you can just set the stream to the Camera monitor/window.  For other streams, just hit "Start Streaming" in OBS and use the OBS Virtual Camera as your video for your stream.  I have done this a fair number of times when one or more players get hit by the internet gremlins.  The exact setup varies by streaming tool, so you might need to search for how to connect a window/screen or OBS to your streaming service.

<h3>Post Production</h3>

This may be the easiest or hardest part of the whole process, depending on how much work you want to do, and it will vary considerably based on the tools you use.  So I am not going to try to explain the entire concept of video editing, or how I do it in my tool of choice.  Instead, I'll list out what I do for my session videos:
- **Add a Title Card and Title:**  This is a piece of evocative art and the name of the session/episode. I used to do this in MS Paint or GIMP.  Now I use DaVinci Resolve, add a video track for art cards and text effects and some fade in/out transitions.
- **Export Title Image:** After I finish the step above, I export a still image of the title for the YouTube title card preview.
- **Add "intermission" cards:** Sometimes the game takes a break or we wipe to a scene or I need to put in a comment or I just want to separate parts of the video.  I use the art portion of the title card for this.  Sometimes I play with transitions here too.
- **Edit Stuff Out:** Breaks, technical issues, discussions that do not serve the game or that I think are not appropriate to share on YouTube, long chunks of no one talking, etc.  I cut these out.
- **Add Commentary:** If I think I need to add text, video, or audio commentary, I cut it in.  This does not happen often in session videos.
- **Balance Audio Levels:** This is wonderful.  Since I use multitrack audio, I can balance each audio source and hear the mix as I balance it.  If you watch my older videos I was using software that had very limited capabilities in this regard.  Now I am using a more powerful tool and it gives me a lot more control over whole tracks, lets me adjust parts of tracks, etc...
- **Adding Markers:** This is a relatively new one for me.  I am using track markers and exporting those markers, with timestamps, to create the YouTube chapters as I do the audio balancing.  Pretty nifty, and a way to combine the two most time consuming tasks in my session videos!
- **Render:** I render to mp4 at 1080p / 24 frames per second.  Choose the format and fps that best fits your desired content!

This checklist takes me about 20 to 40 minutes to actually do, and then rendering a 3 hour video usually takes about half an hour.  Then I upload the video to YouTube and do all the YouTube stuff.

So there you have it!  A high level overview of how I record and produce my session videos.  I hope this is helpful, and thanks for reading!
