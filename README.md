# RailDriver

Smart Locomotive Control script for Garry's Mod Train Build.

## Written & developed by

Cassandra "ZZ Cat" Robinson.

## Warning

RailDriver is still undergoing active development & is not yet ready for prime time release.
If you choose to use RailDriver in its current state, do so at your own risk.
Some features may be broken, bugged, untested, missing, or the script as a whole may resemble a pigeon flying by swinging its head around in circles.

Fear not! I am constantly working on this project (aside from flying my helicopters & helping out with other heli-related projects) & I have every intention of making that stubborn pigeon fly by using its wings. No matter how much the basterd wants to insist on swinging its head around in circles to fly. =^/.~=

## Description

Do I need to categorize my readmes like this anymore? Seems a bit stuffy, to me. It's my GitHub, afterall. Anyways...

This is a little side-project of mine that I have been slowly, but surely whittling my way through over the last year & a half.

My main target for this project is for those that want to just run their trains, & have none of the fuss what normally comes with the territory of running trains in GMTB servers.

The control interface is greatly simplified, & you have everything you need to get going within minutes of showing up in your favorite GMTB server.

## Software License

As always, I believe in freedom & I want to pass that freedom onto you.
Which is why I am proud to license RailDriver to you under the GNU AGPL v3.

## The Start of The Road

I have decided to publish RailDriver stupidly early on in the piece.
I am a bit more clued up on how to properly use GitHub & all its wonderful features, along with using a new IDE: Visual Studio Code. I absolutely adore VS Code, because it has helped streamline 95% of my workflow & I have done all I can to have it work for me... & it delivers the goods... _in spades!!!_
Okay, I digress. Where was I? Oh yea. Now, I remember. This is what you're here for:

- [x] PIDF controller.
  - This has pretty much been my Control Theory playground for the last three years & I have a much older version of this working already.
  - This will be a standard PID controller, where I pull the Feedforward terms in from external sources such as how much of an incline your locomotive is on.
  This will help out, when you're climbing or descending hills.
  - I already have a working feature called "I Term Decay", where this makes stopping the locomotive _that_ much smoother & it also stops the locomotive from rolling backwards & running away (so-called a "Rollback Runaway Condition").
  - I want to implement a feature called "I Term Relax" where the control loop doesn't need to be as reactive to the environment, when the locomotive is running on a flat & level grade of track.
  I am also expecting this to benefit running around with only the locomotive on its own & you don't have any rolling stock in tow.
  - I will also seperate out the I Term Limit.
  Currently, its limit is the same as the PIDF Controller's output to the trucks.
  By making it seperate, this gives you more adjustment over how sensitive you want the control loop to be.
- [ ] Simplified Primary Control Interface.
  - If you're new to the world of GMTB, this will be your best friend.
  - Here, I will have RailDriver automatically select your line speeds based on what map you are running your locomotive on.
  EG for gm_sunsetgulch your linespeeds will be 5, 15, 20, 30, 40 & 60 miles per hour.
    - I _need_ to be careful of how I implement this, due to the temptation of implementing a feature that prevents you guys from overspeeding, based on what linespeed zone you're in.
    I want to avoid doing that as much as I can, because I view something like overspeed prevention as me taking your choice away by imposing unethical restrictions on you.
- [ ] Automatic coupler approach.
  - This will automatically slow your locomotive down to a safe speed when you are approaching your rolling stock, & when your locomotive is coupled to your rolling stock, it will automatically stop.
  I will make it so that all of this is independent of where your set speed is at (if your locomotive is already moving).
  Thus stopping you from ramming into your rolling stock at full speed.
- [ ] A new wireless control link protocol that I have aptly named "DLCT".
  - This one in particular is gonna be exciting, because you won't need to wire anything by hand ever again.
It will also have its own authentication (among other brilliant features) & I will make it _very_ robust & interference free. You're welcome. =^/.~=
- [ ] PID-assisted Emergency Stop.
  - This will use the PIDF control loop to help stop the entire train as quickly as possible.
  - I will make this so that it can be manually triggered as well as automatically triggered by things such as derailment detection.
- [ ] OTA automatic updates.
  - This will be completely transparent to you.
  You virtually will not need to lift a finger in order to keep the E2 updated, when I release new updates.
  - Once I have the PIDF controller working & I give you some basic locomotive controls for you to drive around with, I _really_ wanna focus on this & get it done for you _before_ I start implementing anything else.
  I know updating E2s can be a pain. So, I want to make this as easy for you as the Expression 2 environment will allow me to make it.
  - My primary goal here is to have RailDriver automatically update itself whenever I make new releases of the E2 script.
  IE RailDriver will automatically download code right from this very repository, install it & upload the newly updated script to your in-game session.
  - My secondary goal with this is you won't need to open up the Expression 2 environment to configure the script.
  I will have RailDriver save your configurations for your current locomotive & it will automatically load that in for your locomotive.
- [ ] RailDriver Configurator.
  - Yes. RailDriver will have its own configuration window that you will be able to open & customize RailDriver to your locomotive, tune its PIDs, assign your control keys etc.
- [ ] Wireless Multiple Unit.
  - Once I have DLCT working, you will be able to couple multiple locomotives together & they will automatically configure themselves as a "Multiple Unit".
  I will also give you guys an option to mark which locomotive is the leading locomotive of the MU. At the same time, this will transparently set the other locomotives in your MU as trailing units.
- [ ] Wireless Distributed Power.
  - Very similar to an MU setup & I will make the process of gearing this up equally as simple & transparent.
  - Again, it will rely on DLCT for wireless transmission of control & telemetry data.
  - Once this is implemented, all you will need to do is tell RailDriver which locomotive is the one that you're driving (by simply hopping into your driver's seat) & RailDriver will do _all_ of the heavy lifting for you to set up your Distributed Power Units. All you need to do is hop into your driver's seat & go.
- [ ] Automatic Derailment Detection with Emergency Stop.
  - This will be your lifesaver when you're on the rails. Especially when you're in a GMTB server.
  If for _any_ reason you derail, this will alert you & instantly engage Emergency Stop.
  - Once I implement this, you will be able to instantly rerail the entire train without _any_ need to waste time in doing it manually.
