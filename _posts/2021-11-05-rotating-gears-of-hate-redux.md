---
layout: post
title: Rotating Gears of Hate Redux
date: 2021-11-05 11:15
author: grimmash@gmail.com
comments: true
categories: [ttrpg, foundryvtt]
---

**NOTE: This is a rewrite of a prior article I posted a few days ago, and this version is EVEN BETTER!  The old way works fine, but this one is a bit more precise and has animation.**

Prior article [here](https://grimmash.github.io/ttrpg/foundryvtt/2021/11/01/rotating-gears-of-hate.html).

I have made a [video](https://youtu.be/G9p0ru9PstQ) of what we are going to build in action.

Today we will walk through setting up actual rotating gears for the Gears of Hate in Tomb of Annihilation!  We'll be using Foundry VTT, some macros, and a fair bit of patience.

Credit to Erogroth in the TOA discord for actually figuring this out, or at least sharing with us!  More credit to Freeze and Wasp (the creator of the Sequencer mod in Foundry) for helping me figure out a better way to handle all this.

If you see me highlight things like `this`, I am doing so to call out a menu option or type of object or variable type thingy within Foundry.

Fundamentally we are going to set up the map as normal.  Then we add assets for the gears as `tiles`.  Then we set those `tiles` up as `vehicles` using a mod and `draw` tools.  Finally we tie the `drawings`, `tiles`, and some `actors` together in a `macro`.

Let's get started!

# Requirements

- **Foundry VTT** with the following mods:
  - [Vehicles and Mechanisms](https://github.com/grandseiken/foundryvtt-vehicles-and-mechanisms)
  - [Multilevel Tokens](https://github.com/grandseiken/foundryvtt-multilevel-tokens) *this is a dependency of the above*
  - [Sequencer](https://github.com/fantasycalendar/FoundryVTT-Sequencer)
- **Map Art** with *tiles* for the gears
- A little bit of **patience**

You absolutely need some copy of a map, and art assets to use as gears, one asset for each gear.  In my photos I am using a map under development by a fellow DM.  Come find us in the ToA Discord if you want to know more.  Multiple version of art have been posted there that should work for this.  Otherwise, you can use an image editor of your choice to cut out the gears from the map to create your own assets.  

You want the gears assets set up in one of two ways.   Either as `.png` files with transparency that lets them "float" over the background and lets the background through the teeth of the gears, or any other format without transparency if your art has water between the teeth that matches the background map art.  

Before you start, make sure you active the **Multilevel Tokens**, **Vehicles and Mechanisms**, and **Sequencer** modules in game.  **Vehicles and Tokens** lets you define a `drawing` object as a `vehicle` and capture other objects on the canvas as your vehicle.  **Multilevel Tokens** is a requirement for **Vehicles and Mechanisms**.  **Sequencer** is going to let us define a much simpler macro than the prior article and get some nice effects built in.

# Building the Rotating Gears

1. Get your map art loaded into a `scene`.
2. Outside Foundry, figure out your map's pixel to grid ratio.  I use 100px to a 5ft square because it is very easy to handle all sorts of conversions and technical stuff.  If you are using the roll20 or DnD Beyond art, they have a 70px grid, if I recall correctly.  All that matters is that you know you pixel to grid settings.
3. Resize the three images of your gears to exactly fit a given space on the map.  If your grid is 100px, make the gears 100 x the number of squares it will cover. You may need to play around with this.  In my case, my gears are 1200px squares, covering a 12x12 square space on the map.
4. Place the gears as `tiles` on the map.  If your assets are an even number of squares in size, make sure the center pivot of the tile is at a grid intersection.  If your assets are an odd number of squares in size, make sure the center is in the middle of the middle square of the area.  At this point, you may need to play around with the best size of your assets to match your map.  Here are mine:

  ![New gears](/media_assets/gears_of_hate/3_new_gears.png)
5. `Draw` a square that contains your gear `tile` and the are where you will have your `walls`.  In my example above I made my square a 1000px x 1000px square and positioned it exactly so that the middle was the center point of rotation for each gear, and it contained my `walls`.  You can manually adjust the location and size of a `drawing` if you double click on it.
6. Add your `walls`, `lights`, and whatever else you want on the gear.
7. Create three `characters` (type does not matter) with easy to recall names that will represent you gears.  I like something along the lines of `Gear1`, `Gear2`, `Gear3`.
8. Place `tokens` for those characters on the map, preferably somewhere outside the `walls` where the PCs could ever see them.  You could also just hide them, but I like having them off on the far side of the map.  This way I can check the rotation of the `tokens` later if needed.
9. Double click the `drawing` object to bring up the object's menu, and navigate to the `Vehicles` tab.
10. Set the following options:
  - `Capture Tokens: Auto`
  - `Capture Tiles: Manual`
  - `Capture Walls: Manual`
  - `Name of Controller Token`: the name you gave for the `character` created above for this gear.
11. Click `Update Drawing`
12. Right click the `drawing` object and on the right side, click the `Capture Now` button.  It looks like a steering wheel.  There is also a `Release` button if you need to undo this to fix `walls` or something else later on.

So what just happened?  You are using the `drawing` object to define the `vehicle` that is your gear.  It will later apply the movement effects we will define in a `macro`.  You absolutely need to make sure all the `walls` are completely within the boundary, otherwise the segments that pass through `drawing` boundary will NOT rotate.  We are setting `Capture Token` to `Auto` so that any token within the circle will get caught when we later activate the `macro`.  We are `manually` capturing the `walls` and `tiles` (the gear) so nothing weird happens down the road, and we can adjust things.

Now do steps 5 through 12 again for EACH gear.  Once you have finished, you have set up the three `vehicles` we are going to manipulate with `macros`.

# Making the Macros

Now for the scary part.  We are going to do some coding.  My previous article made five macros, we are going to simplify this, and use only one `macro`.

1. If you don't have any `macros` in your `hotbar` at the bottom of the screen, click the first empty space.  This will open a new `macro`.
2. Set the `name` to "Gear Sequencer" or something like that.
3. Set `Type` to `script`
4. Paste the code below in:
    Each macro will follow this pattern:

    ```
    let token1 = canvas.tokens.placeables.find(t => t.data.name === "TorGear1");
    let token2 = canvas.tokens.placeables.find(t => t.data.name === "TorGear2");
    let token3 = canvas.tokens.placeables.find(t => t.data.name === "TorGear3");

    new Sequence()
      .sound("Audio/Sounds/gears_of_hate_2_15s.mp3")
      .animation()
        .on(token1)
        .rotateIn(token1.data.rotation + 72, 2000,{ease: "easeInOutCubic",delay: -1000})
      .animation()
        .on(token2)
        .rotateIn(token2.data.rotation - 72, 2000,{ease: "easeInOutCubic",delay: -250})
      .animation()
        .on(token3)
        .rotateIn(token3.data.rotation + 72, 2000,{ease: "easeInOutCubic",delay: -250})
      .play();
    ```
    Here is an image, using names and variables from my game:

    ![Sample Macro](/media_assets/gears_of_hate/4_gears_sequencer_macro.png)

    Let's pause and dissect this a bit so you understand what is happening.

    ```
    let token1 = canvas.tokens.placeables.find(t => t.data.name === "Gear1")
    ```
    This code is creating a variable in the script that is assigning the token1 value to your first `character`, which is also the controller of the `vehicle` we created.  We do this for each gear.  
    ```
    new Sequence()
    ```
    This is telling the macro to create a new **Sequencer** sequence.
    ```
      .sound("Audio/Sounds/gears_of_hate_2_15s.mp3")
    ```
    This is playing a sound at the start of the sequence that will play.
    ```
    .animation()
      .on(token1)
      .rotateIn(token1.data.rotation + 72, 2000,{ease: "easeInOutCubic",delay: -1000})
    ```
    This is creating an animation.  That animation is affecting `token1`.  The animation will rotate when we tell it to play.  The method is `.rotateIn(degrees, duration, options)`.  You only need to put in the `degrees` to tell it how far to rotate the token.  The `duration` is the length of the animation in milliseconds, so in this case we are telling it `2000ms` or 2 seconds.  The `options` can be extensive, in this case I am using `ease` to call another library to smooth the graphics out a bit.

    Full documentation for **Sequencer** is [here](https://github.com/fantasycalendar/FoundryVTT-Sequencer/wiki).

    You can find some of the `ease` options [here](https://easings.net/).

    We do this for each gear, so all three animate.  I have my gears each rotating 72 degrees.  Some have positive and some have negative rotation values, due to the way the gears work.
    ```
      .play();
    ```
    This tells the macro to do all the stuff we just told it to do when we click the button in the hotbar.

5. Make sure where I wrote "Gear1", "Gear2", "Gear3", replace with your own names for the `characters` and the `controller` you created and set earlier.
6. Save the `macro`.

Now when you click the `macro` it should play the sound (optional), rotate the `tokens` controlling the gears, and in doing so will rotate the gears, their `tiles`, `walls`, and any `tokens` standing inside the gears through to the next configuration.

If you want you could in theory combine this with my preivous article to both have absolute position macros and the dynamic, animated macro.

In case you need it for reference, the rotational positions for each gear in each configuration are below:

| Position | Gear 1 Degree | Gear 2 Degree | Gear 3 Degree |
|-|-|-|-|
|1|0|0|0|
|2|288|72|288|
|3|216|144|216|
|4|144|216|144|
|5|72|288|72|

Also, in case you want to get fancier, the Foundry Macro page is [here](https://foundryvtt.com/article/macros/).

And that is it!  Good luck and have fun!

# Troubleshooting

If something is not working right, check each step from the beginning.  It may take a few tries to get this right.  I had to try about 3 times to get it all working.  I ran into issues at most steps, and have tried to explain as much as I can here without going into insane depth.  If you get stuck, either take a break an/or just start over. Test this before you use it, and if you add sound, test as a player!

Good luck and have fun!
