# RailDriver

Smart Locomotive Control script for Garry's Mod Train Build.

## Written & developed by

Cassandra "ZZ Cat" Robinson.

## Warning

RailDriver is undergoing active development & is not yet ready for prime time release.
If you choose to use RailDriver in its current state, do so at your own risk.
Some features may be broken, bugged, untested, missing, or the script as a whole may resemble a pigeon flying by swinging its head around in circles.

Fear not! I am constantly working on this project (aside from flying my helicopters & helping out with other heli-related projects) & I have every intention of making that stubborn pigeon fly by using its wings. No matter how much the basterd wants to insist on swinging its head around in circles to fly. =^/.~=

If you have spotted any bugs, something isn't working the way it should, or you have any suggestions on what you want to see in RailDriver, don't hesitate to open an Issue.

## Description

This is a little side-project of mine that I have been slowly, but surely whittling my way through over the last year & a half.
Recently, it has evolved exponentially since I had internet installed at my place (after not having any for six years).

My main target for this project is for those that want to just run their trains, & have none of the fuss what normally comes with the territory of running trains in GMTB servers.

The control interface is greatly simplified, & you have everything you need to get going within minutes of showing up in your favorite GMTB server.
All you need to do is spawn RailDriver's E2 chip on your locomotive's body & go!

## Installation

Part 1 of 2 of Over-The-Air Updates is now [live](https://github.com/ZZ-Cat/RailDriver/pull/26)!
Once you have placed RailDriver into your ```e2shared``` directory, you can use ```.raildriver update local``` to update RailDriver instead of using Expression2's editor & your toolgun to keep RailDriver updated.

### Prerequisites

You need these before you can use RailDriver.

- [Garry's Mod](https://store.steampowered.com/app/4000/Garrys_Mod)!
- [Wiremod](https://steamcommunity.com/id/wireteam/myworkshopfiles/?appid=4000)!
- [The FC&N Server Addons Pack](https://steamcommunity.com/sharedfiles/filedetails/?id=390798140).
It's not imperative that you use literally everything in this addon pack.
But, I highly recommend you at the _very least_ get the following items:
  - [gm_sunsetgulch](https://steamcommunity.com/sharedfiles/filedetails/?id=311697867)
    - If you go this route, you _will_ need to install [Half-Life 2: Episode 2](https://store.steampowered.com/app/420/HalfLife_2_EpisodeTwo) to see some of the texturess in that map.
    - You _will_ also need [Magnum's Trakpak 2](https://steamcommunity.com/sharedfiles/filedetails/?id=391016040).
  - [Grovestreetgman's Propper Trains](https://steamcommunity.com/sharedfiles/filedetails/?id=1195015027)
  - [Grovestreetgman's Shared Textures](https://steamcommunity.com/sharedfiles/filedetails/?id=676234187)
  - [Grovestreetgman's Train Parts](https://steamcommunity.com/sharedfiles/filedetails/?id=276309010)
  - [Grovestreetgman's Train Sounds](https://steamcommunity.com/sharedfiles/filedetails/?id=240020348)
  - [Magnum's Train Model Pack (Consolidated)](https://steamcommunity.com/sharedfiles/filedetails/?id=260954002)
  - [Magnum's Trakpak 2](https://steamcommunity.com/sharedfiles/filedetails/?id=391016040)
    - **NB:** This _is_ discontinued, but is still being maintained, & it is required if you want to run in Sunset Gulch.
      [TrakPak 3](https://steamcommunity.com/sharedfiles/filedetails/?id=2379202601) is its successor.
  - [The Big Propper Train Shared Texture Pack](https://steamcommunity.com/sharedfiles/filedetails/?id=1227050421)

By rights, you should also at least have one locomotive already pre-made.
If you don't have this, you need to do some prep-work:

1. A locomotive body blank. I highly recommend starting off with an SD40.
2. Your locomotive _must_ have a set of trucks _axis contrained_ to the body.
The SD40 uses ```locobogey3.mdl```.
You _can_ also use Advanced Ballsocket constraints on the trucks in place of the axis constraint,
but this is known to cause stability & derailment issues.
3. A Wire Gate attached to your locomotive's body. **DO NOT PARENT IT YET!**
4. Your seat of choice frozen in place in the locomotive's cabin.
5. Now, parent your seat to the Gate, & _then_ parent the gate to the Locomotive's body.

RailDriver uses several Expression2 extensions that may be disabled by default.
If this is the case, you need to enable the following extensions:

- chatprint - This is used to alert you to any of RailDriver's errors.
- file - This is used by Local OTA Updates.
- http - When Online OTA Updates is implemented, this is how RailDriver will go about it.
- propcore - For things like ```E:applyForce()```. Your locomotive will not go anywhere without it.
- remoteupload - Local OTA Updates uses this to update RailDriver's E2 chip.
- serialization - The Version File is encoded in .json format. RailDriver uses this to decode & encode the Version File.
- vgui - Configurator will use this, when it is implemented in a future release.

### Download RailDriver

1. Click the green code button & hit "Download ZIP".
2. Extract that to your directory. EG ```SteamLibrary\steamapps\common\GarrysMod\garrysmod\data\expression2```
3. You _must_ put RailDriver into your Expression 2's ```e2shared``` folder in order for it to work correctly.
Local OTA Updates are now live, & if RailDriver is anywhere _but_ your ```e2shared``` folder it _will not_ function & things will be broken.

If you have already updated RailDriver since #26 has been merged, this is where you can use ```.raildriver update local``` in Garry's Mod's in-game chat to update RailDriver.
If this is your first time installing RailDriver ever, follow the instructions in the section below.

### Fire up Garry's Mod

Now that Local OTA Updates are live, you only need to do this once-only, as RailDriver's Local OTA Updates can be used in place of this.

This section takes place in your tool gun. So, make sure you have Expression2 selected.

1. In your ```e2shared``` folder, double-click on the ```RailDriver``` folder, & double-click ```RailDriver.txt```.
2. Aim your toolgun at your locomotive & spawn RailDriver's E2 chip in an inconspicuous spot.
3. That's all there is to it.

Once RailDriver has initialized, you will be greeted with ```Welcome to RailDriver!``` & ```Type '.raildriver help' for a list of commands.``` in Garry's Mod's in-game chat.

### When you use RailDriver

Here's some helpful tips for when you're using RailDriver:

- You _do not_ need to parent RailDriver's E2 to your locomotive's body. Because I have coded RailDriver to take care
of this for you, as a part of RailDriver's Smart Entity Management.
- You _do not_ need to do any wiring whatsoever.
RailDriver has no physical I/Os.
In later releases, I will start bringing in DLCT, which is a wireless protocol to communicate to other DLCT compatible E2s.
- If you're in a multiplayer server, RailDriver's E2 _will_ seem like it has disappeared from your locomotive, once everything has initialized. Don't worry, your E2 hasn't gone anywhere. It's still there. This is normal behavior, because Smart Entity Management has now hidden your E2 & made it virtually inaccessible to other players.
This is a convenience measure, as it provides peace-of-mind from would-be griefers that are smarter than your average troll.
- If you need to reboot/restart/reset RailDriver, type ```.raildriver restart``` into your chat.
- If you need to  update or restart RailDriver, stop your locomotive first.
This will put RailDriver in a known state during the update & restart processes.

### Notes about ops count & tick quotas

RailDriver is reasonably computationally intensive for an Expression2 script.
This is due to the fact that RailDriver uses a PIDF Control Loop to manage your locomotive's speed, throttle, braking, acceleration & deceleration. The control loop uses E2's ```tickClk()``` for execution, & the control loop is constantly running. Even when your locomotive has stopped.

RailDriver's speedometer uses differential inputs that are sourced from your locomotive's bogeys & are converted into a single speed value. This value is then sent through a low-pass filter to reduce the amount of noise that is picked up by the bogeys.
The control loop uses this speed value as its feedback to manage the locomotive's speed in a smooth & precise manner.

There is a vast amount of checks-&-balances that are strategically placed throughout RailDriver's source code, that are constantly monitoring your locomotive's primary operations. This is to ensure RailDriver is running smoothly & reliably at all times.

All of this equates to RailDriver's average ops count being around 1950~2000 ops. I strongly advise you either use ```wire_expression2_unlimited 1``` or you set your Expression2 soft & hard quotas accordingly.

If you get a ```RailDriver Tick Quota Exceeded``` error, it is likely that your Tick Quota is too low.
Increase your Tick Quota to at least 50,000 or higher by typing ```wire_expression2_quotatick 50000``` into Garry's Mod's console, followed by ```wire_expression2_reload```.

I am also aware that not all multiplayer servers keep their versions of Expression2 up-to-date.
If you're seeing a compilation error regarding the ```@strict``` directive or the ```try``` & ```catch``` statements, this is likely because the server that you're in is using a wickedly outdated version of Expression2 & the server owners haven't updated it yet. This is certainly the case for RailDriver's target server: The Flatgrass Construct & Northern Railroad.

I do have a branch called FC&N-Optimizations which removes the ```@strict``` directive & the exception handlers.
This branch sacrifices some reliability in favor of backward-compatibility.
This branch is now grossly outdated, as I am continuously updating only the Main-Trunk, & I will eventually delete that branch altogether.
If there is enough demand for it, I will do a version of RailDriver with the ```@strict``` directive & the exception handlers removed. I will consider this my LTS (Long-Term Support) version of RailDriver, where updates to this code will happen exponentially slower. Additionally, it won't be as feature rich or as computationally intensive as RailDriver.

## Software License

As always, I believe in freedom & I want to pass that freedom onto you.
Which is why I am proud to license RailDriver to you under the [GNU Affero GPL v3](https://github.com/ZZ-Cat/RailDriver/blob/Main-Trunk/LICENSE.md).

## The Road so far

RailDriver is fastly approaching its first official Release Candidate! =^/,..,^=
Here is a list of what's working in RailDriver, so far:

- Command-Line Interface
  - The CLI uses Garry's Mod's in-game chat. It's not the prettiest of CLIs, but it's functional.
  - All commands in the CLI are case-insensitive.
  - Every command is prefixed with ```.raildriver```
  - Here is a list of commands that I have implemented so far:
    - ```about``` - Displays information about RailDriver, whom the author is, what license RailDriver has,
    & where you can go to obtain RailDriver's source code (by rights, the link should point you back here).
    Also, it displays the current version of RailDriver.
    This information is now sourced from the Version File.
    - ```controls``` - Want to know what your key bindings for driving your locomotive are? This is your port of call!
    - ```help``` - Shows a list of commands that are available to you in the CLI.
    - ```restart``` - This restarts RailDriver. It's analogous to looking at an E2 & pressing your 'Reload' key.
    - ```update``` - Over-The-Air Updates.
      - Arguments
        - ```local``` - Updates RailDriver from your ```e2shared/RailDriver``` directory.
        - ```online``` - Coming soon. When I implement Online Over-The-Air Updates, you will be able to use this command.
- Over-The-Air Updates Part 1 of 2 - Local
  - This uploads RailDriver's code directly to its E2 chip in-game from your ```e2shared/RailDriver``` directory.
- PIDF Controller
  - All speed values going to the PIDF Controller are in Source Units.
  - Feedforward is derived from the Set Point.
  - I-Term Decay bleeds off the control loop's I-Term when you tell your locomotive to stop.
    It starts bleeding the I-Term off at around 3 MPH. Not only does this make the train stop
    a lot smoother, it also stops the locomotive from rolling backwards & running away (so-called
    a "Rollback Runaway").
- Simplified Primary Controls!
  - This is helped by & large by the control loop.
  - Currently, you are driving your locomotive in a mode I call "Velocity Mode"
    (Don't worry, there are two new modes to come in later versions).
    Velocity Mode can be thought of as being analogous to your car's Cruise Control,
    where you set the speed of the train & the control loop will do whatever it can to keep
    your train moving at that speed, regardless of the track conditions.
- Smart Emergency Stop.
  - This is activated by pressing your ```Emergency Brake``` key. By default, this is the spacebar.
  - This uses an observer to monitor the locomotive's speed, as it comes to a stop.
    It monitors the locomotive at 2 Hz, which makes it incredibly fast acting, when something goes awry.
    You guys will get a kick out of this. Here's the stages in which it operates:
    1. **"Stop the locomotive!"** - This is where you have commanded your locomotive to stop,
    & the control loop is stopping your entire train.
    2. **"I hope it stops."** - This state monitors your locomotive's speed & if the locomotive is still
    not stopping, tougher measures will be taken.
    3. **"I wasn't asking!"** - At this point, the control loop isn't enough to stop the train.
    The automatic brakes are fully applied as a secondary attempt to stop the train.
    4. **"You should've listened!"** - This state determines if the train is still running away.
    If your train still isn't slowing down at this point, it's basically running away uncontrolled.
    There's only one thing for it...
    5. **"You can't runaway, if you're frozen!"** - This state is something that you more-than-likely _don't_
    want to encounter. Your entire train is frozen & RailDriver will have shut everything down (save for the
    Command-Line Interface), & you will need to restart RailDriver & unfreeze your train.
    But first, assess what caused your train to runaway uncontrolled in the first place.
- Speedometer
  - Uses differential inputs in Source Units, taken from both the front & rear trucks of the locomotive.
  - A low-pass filter & a deadband is used to reduce the amount of sensor noise.
  - The Speedometer is used for speed data acquisition for the control loop's feedback input.

Next up is what I want to put in RailDriver, before I get the first Release Candidate out the door:

- [ ] Over-The-Air Automatic Updates.
  - [x] Local Over-The-Air Updates are now live.
  - [ ] Online Over-The-Air Updates. This is where I am currently at.
  - I was right. This is taking me a while to put together. But, bear with me, as I am now making a start on the Online portion of OTA Updates. Once this goes live, I will announce RailDriver's first Release Candidate for v1.0.0.
- I will also put together a Discord Server for RailDriver, so you guys can easily get in touch with me & we can turn RailDriver into a community-driven project. =^/,..,^=

...& Finally, this is what is yet to be implemented, but is on my TO-DO List, & will show up in later releases:

- [ ] Automatic coupler approach.
  - This will automatically slow your locomotive down to a safe speed when you are approaching your rolling stock, & when your locomotive is coupled to your rolling stock, it will automatically stop your locomotive.
  I will make it so that all of this is independent of where your set speed is at (if your locomotive is already moving).
  Thus stopping you from ramming into your rolling stock at full speed.
- [ ] A new wireless control link protocol that I have aptly named "DLCT".
  - DLCT stands for Digital Locomotive Control & Telemetry.
  - Eventually, I want to create my own ecosystem of E2s that use DLCT, starting with RailDriver.
  - This one in particular is gonna be exciting, because you won't need to wire anything by hand ever again.
It will also have its own authentication (among other brilliant features) & I will make it _very_ robust & interference free. You're welcome. =^/.~=
- [ ] Fix up Player Controls.
  - Currently, whenever you leave your locomotive's cabin, you still have full control of your locommotive,
  & there is no way to turn this off. I will fix this up by bringing in the ability to use Remote Control Mode.
  I don't know how I'm gonna do this just yet. But, I'll cross that bridge when I get there.
- [ ] RailDriver Configurator.
  - Yes. RailDriver will have its own configuration window that you will be able to open & customize RailDriver bespoke to your locomotive; you will be able to tune PIDs, tune filters, adjust your line speeds, assign your control keys etc.
  - This will likely, by & large, draw heavy inspiration from the likes of BetaFlight Configurator & RotorFlight Configurator (Don't worry, I will give credit where credit is due).
- [ ] Wireless Multiple Unit.
  - Once I have DLCT working, you will be able to couple multiple locomotives together & they will automatically configure themselves as a "Multiple Unit".
  I will also give you guys an option to mark which locomotive is the leading locomotive of the MU. At the same time, this will transparently set the other locomotives in your MU as trailing units.
- [ ] Wireless Distributed Power.
  - Very similar to a MU setup & I will make the process of gearing this up equally as simple & transparent.
  - Again, it will rely on DLCT for wireless transmission of control & telemetry data.
  - Once this is implemented, all you will need to do is tell RailDriver which locomotive is the one that you're driving (by simply hopping into your driver's seat) & RailDriver will do _all_ of the heavy lifting for you to set up your Distributed Power Units. All you need to do is hop into your driver's seat & go.
- [ ] Automatic Derailment Detection with Emergency Stop.
  - This will be your lifesaver when you're on the rails. Especially when you're in a GMTB server.
  If for _any_ reason you derail, this will alert you & instantly engage Emergency Stop.
  - Once I implement this, you will be able to instantly rerail the entire train without _any_ need to waste time in doing it manually. Yes, this draws inspiration from Magnum MacKivler's own Fender Bender Defender.
