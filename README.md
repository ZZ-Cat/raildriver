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
