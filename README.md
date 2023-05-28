# RailDriver

Smart Locomotive Control script for Garry's Mod Train Build.
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/ZZ-Cat/CRSFforArduino)](https://github.com/ZZ-Cat/RailDriver/releases/latest)
[![GitHub license](https://img.shields.io/github/license/ZZ-Cat/CRSFforArduino)](https://github.com/ZZ-Cat/RailDriver/blob/Main-Trunk/LICENSE.md)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)

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

## RailDriver-LTS

RailDriver-LTS can be found [here](https://github.com/ZZ-Cat/RailDriver/tree/RailDriver-LTS).

RailDriver-LTS offers Long-Term Support, & is backwards-compatible with Garry's Mod Train Build servers that are using legacy versions of Expression2. RailDriver-LTS is updated roughly once per year & when it's absolutely necessary to do so.

## Software License

As always, I believe in freedom & I want to pass that freedom onto you.
Which is why I am proud to license RailDriver & RailDriver-LTS to you under the [GNU Affero GPL v3](https://github.com/ZZ-Cat/RailDriver/blob/Main-Trunk/LICENSE.md).

## The Road so far

I am no longer managing my projects via the main readme of each project.
If you want to see an overview of where I am at with any of my projects, you can check out my [Projects tab](https://github.com/ZZ-Cat?tab=projects) on my profile.
You can also look at my Issues & Pull Request tabs. Occasionally, I use my Issues tab for writing little "notes to self" to remind myself about something that I need to add/remove/fix in a relevant repository.
My Pull Requests are where _all_ of my development on any of my projects takes place. I update them from time-to-time, whenever I am working on a feature in a particular repository.
