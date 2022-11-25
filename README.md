# RailDriver-LTS

[RailDriver](https://github.com/ZZ-Cat/RailDriver) with Long-Term Support.

## Written & developed by

Cassandra "ZZ Cat" Robinson.

## Warning

RailDriver is still undergoing active development & is not yet ready for prime time release.
If you choose to use RailDriver in its current state, do so at your own risk.
Some features may be broken, bugged, untested, missing, or the script as a whole may resemble a pigeon flying by swinging its head around in circles.

Fear not! I am constantly working on this project (aside from flying my helicopters & helping out with other heli-related projects) & I have every intention of making that stubborn pigeon fly by using its wings. No matter how much the basterd wants to insist on swinging its head around in circles to fly. =^/.~=

## Description

RailDriver-LTS is the long-term support version of [RailDriver](https://github.com/ZZ-Cat/RailDriver), the smart locomotive controller script for Garry's Mod train buld servers. It trades a certain level of reliability to focus on the retention of backward-compatibility with Garry's Mod train build servers that use older/outdated versions of Expression2.

This means that updates to RailDriver-LTS are happening exponentially slower than its Main-Trunk counterpart.

## Features

RailDriver-LTS is _not_ as feature rich as its Main-Trunk counterpart.
This means that things such as the CLI, Detailed Fault Handling, Exception Handling, DLCT, Over-The-Air Updates etc are _not_ present, as these things require the very latest version of Expression2 in order to function.
With that being said, basic functionality between RailDriver & RailDriver-LTS is, by & large, the same. IE You more-than-likely won't notice any difference between either branch, when it comes to your locomotive's driving behavior.

The following list of items are what you get with RailDriver-LTS:

- Player Controls.
  - Default keys are as follows:
  - Emergency Brake: Spacebar
  - Reverser (Decrease): S
  - Reverser (Increase): W
  - Throttle (Decrease): A
  - Throttle (Increase): D
- PIDF Control Loop.
  - Constantly running, even when the locomotive has stopped.
  - Fixed mode: Velocity Mode - Behaves in the same way as Cruise Control.

Anything that is not listed here is _not_ included in RailDriver-LTS.

## Installation

Downloading & installing RailDriver-LTS is the same as downloading & installing RailDriver.
Only here, the requirement for putting RailDriver-LTS into your ```e2shared``` folder is _not_ as critical as it is with RailDriver.

If you do opt to install RailDriver-LTS in your regular ```expression2``` folder, you will need to remove the ```e2shared``` portions of the file paths in the includes in ```RailDriver.txt```.

## Final notes

Bugs that were resolved in later releases of RailDriver may still be present in RailDriver-LTS.
IIRC, there are two known issues (#21 & #30) that are still present in RailDriver-LTS.
Eventually, I will get around to fixing these in RailDriver-LTS. However, this is not a priority for me at this time, as I am primarily focusing on developing RailDriver.

This is merely a minder to be aware of these two bugs, as they _do_ cause significant reliability issues.
For the time being, as a workaround, a.) Do not spawn RailDriver-LTS' E2 on anything other than a valid locomotive body (that also has trucks that are either axis constrained or advanced ballsocket constrained to the body); & b.) When using the Advanced Duplicator with your locomotive, you need to go ahead & manually reset RailDriver-LTS.

If you are in a server, & RailDriver-LTS' E2 has disappeared, you need to go into the Expression2 editor's Remote Uploader & click ```Reset```. This will remotely restart RailDriver-LTS. You will also need to do this when RailDriver-LTS freezes your entire train, when it detects a major fault.
