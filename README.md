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

## Installation

Until I get OTA Updates out the door, you're stuck with doing this The Old School Way, for now. =^/.~=

### Prerequisites

You need these before you can use RailDriver.

- Garry's Mod!
- Wiremod.
- The FC&N Official Server Addons Pack.
It's not imperative that you use literally everything in this addon pack.
But, I highly recommend you at the _very least_ get the following items:
  - gm_sunsetgulch
    - If you go this route, you _will_ need to install Half-Life 2: Episode 2 to see some of the texturess in that map.
  - Grovestreetgman's Propper Trains
  - Grovestreetgman's Shared Textures
  - Grovestreetgman's Train Parts
  - Grovestreetgman's Train Sounds
  - Magnum's Train Model Pack (Consolidated)
  - Magnum's Trakpak2
  - The Big Propper Train Shared Texture Pack

By rights, you should also at least have one locomotive already pre-made.
If you don't have this, you need to do some prep-work:

1. A locomotive body blank. I highly recommend starting off with an SD40.
2. Your locomotive _must_ have a set of trucks _axis contrained_ to the body.
The SD40 uses ```locobogey_3```.
You _can_ also use Advanced Ballsocket constraints on the trucks in place of the axis constraint,
but this is known to cause stability & derailment issues.
3. A Wire Gate attached to your locomotive's body. **DO NOT PARENT IT YET!**
4. Your seat of choice frozen in place in the locomotive's cabin.
5. Now, parent your seat to the Gate, & _then_ parent the gate to the Locomotive's body.

### Download RailDriver

1. Click the green code button & hit "Download ZIP".
2. Extract that to your directory. EG ```SteamLibrary\steamapps\common\GarrysMod\garrysmod\data\expression2```
3. You need to put RailDriver into your Expression 2's ```e2shared``` folder in order for it to work correctly.
When I implement OTA Updates, the ```e2shared``` folder will be a must for the OTA Updates to work.

### Fire up Garry's Mod

Here, this block takes place in your tool gun. So, make sure you have Expression2 selected.

1. In your ```e2shared``` folder, double-click on the ```RailDriver``` folder, & double-click ```RailDriver.txt```.
2. Aim your toolgun at your locomotive & spawn RailDriver's E2 chip (preferably in an inconspicuous spot).
3. That's all there is to it.

You will be greeted with ```Welcome to RailDriver!``` & ```Type '.raildriver help' for a list of commands.``` in
Garry's Mod's in-game chat.

### When you use RailDriver

Here's some helpful tips for when you're using RailDriver:

- You _do not_ need to parent RailDriver's E2 to your locomotive's body. Because I have coded RailDriver to take care
of this for you, as a part of RailDriver's Smart Entity Management.
- You _do not_ need to do any wiring whatsoever.
RailDriver has no physical I/Os.
In later releases, I will start bringing in DLCT, which is a wireless protocol to communicate to other DLCT compatible E2s.
- If you're in a multiplayer server, RailDriver's E2 _will_ seem like it has disappeared from your locomotive, once everything has initialized. Don't worry, your E2 hasn't gone anywhere. It's still there. This is normal behavior, because Smart Entity Management has now hidden your E2 & made it virtually inaccessible to other players.
This is a convenience measure, as it provides peace-of-mind from would-be griefers that are smarter than your average troll.
- If at any time you need to reboot/restart/reset RailDriver, type ```.raildriver restart``` into your chat.

## Software License

As always, I believe in freedom & I want to pass that freedom onto you.
Which is why I am proud to license RailDriver to you under the GNU AGPL v3.

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
    - ```controls``` Wnat to know what your key bindings for driving your locomotive are? This is your port of call!
    - ```help``` - Shows a list of commands that are vailable to you in the CLI.
    - ```restart``` This restarts RailDriver. It's analogous to looking at an E2 & pressing your 'Reload' key.
- PIDF Controller
  - All speed values going to the PIDF Controller are in Source Units.
  - Feedforward is derived from the Set Point.
  - I-Term Decay bleeds off the control loop's I-Term when you tell your locomotive to stop.
    It starts bleeding the I-Term off at around 3 MPH. Not only does this make the train stop
    a lot smoother, it also stops the locomotive from rolling backwards & running away (so-called
    a "Rollback Runaway").
- Simplified Primary Controls!
  - This is helped by & large by the PIDF Controller.
  - Currently, you are driving your locomotive in a mode I call "Velocity Mode"
    (Don't worry, there are two new modes to come in later versions).
    Velocity Mode can be thought of as being analogous to your car's Cruise Control,
    where you set the speed of the train & the control loop will do whatever it can to keep
    your train moving at that speed.
- Smart Emergency Stop.
  - This uses an observer to monitor the locomotive's speed, as it comes to a stop.
    It monitors the locomotive at 2 Hz, which makes it incredibly fast acting, when something goes awry.
    You guys will get a kick out of this. Here's the stages in which it operates:
    1. **"Stop the locomotive!"** - This is where you have commanded your locomotive to stop,
    & the control loop is stopping your entire train.
    2. **"I hope it stops."** - This state is where the speed is being monitored & if the locomotive still
    not stopping, tougher measures to stop the train will be taken.
    3. **"I wasn't asking!"** - At this point, the control loop isn't enough to stop the train.
    So, the automatic brakes are fully applied to stop the train.
    4. **"You should've listened!"** - This state determines if the train is still running away.
    If your train still isn't slowing down at this point, it's basically running away uncontrolled.
    5. **"You can't runaway, if you're frozen!"** - This state is something that you more-than-likely _don't_
    want to encounter. Your entire train is frozen & RailDriver will have shut everything down (save for the
    Command-Line Interface), & you will need to restart RailDriver & unfreeze your train.
    But first, assess what caused your train to runaway uncontrolled in the first place.
- Speedometer
  - Uses differential inputs, taken from both the front & rear trucks of the locomotive.
  - A low-pass filter & a deadband is used to reduce the amount of sensor noise.

Next up is what I want to put in RailDriver, before I get the first Release Candidate out the door:

- [ ] Over-The-Air Automatic Updates.
  - This is more-than-likely going to take a while to put together,
  because I'm giving you guys a two-for-one-deal, here. Both local updates & online updates.
  - This is where the CLI comes in handy & (by extension) is why I wanted to write the CLI
  _before_ I started work on the OTA updates.
  - Local Updates - What I want to achieve here is, you do ```.raildriver update local``` & it will directly upload RailDriver's code from your game's directory to its own E2 in-game.
  This is the same process that happens whenever you spawn in any E2 in-game.
  I will also benefit from this one, too. Because it will help out with testing & developing RailDriver that bit faster,
  because I'm not having to manually update its code all of the time.
  - Online Updates - Here, you do ```.raildriver update online``` & it will automatically download a new update & install
  it.
  - You won't need to lift a finger here, other than using the CLI to tell RailDriver to update itself.
  I do have an older repository here that demonstrates the possibility of OTA Updates, & this will more-than-likely be an
  expansion of that.
  - I will write in a notification system that lets you know that a new release has been made, & I will give you the choice
  to download it (or not). I _refuse_ to make updates mandatory/compulsory.
  With that being said, I _do_ recommend that you do update RailDriver at every Major (IE 1.x.x, 2.x.x, 3.x.x etc) Release,
  as I will be maintaining compatibility with Wiremod (Expression 2 is a part of this), the FC&N Railroad server,
  & Garry's Mod with only one-or-two major releases of RailDriver.
  I _do_ reserve the right to discontinue older versions, as my focus is on the latest release.
  When I do discontinue an older release, I will give you guys plenty of notice (I'm a nice gal like that) &
  I will do an archive of older releases of RailDriver for your perusal.

...& Finally, this is what is yet to be implemented, but is on my TO-DO List, & will show up in later releases:

- [ ] Automatic coupler approach.
  - This will automatically slow your locomotive down to a safe speed when you are approaching your rolling stock, & when your locomotive is coupled to your rolling stock, it will automatically stop.
  I will make it so that all of this is independent of where your set speed is at (if your locomotive is already moving).
  Thus stopping you from ramming into your rolling stock at full speed.
- [ ] A new wireless control link protocol that I have aptly named "DLCT".
  - This one in particular is gonna be exciting, because you won't need to wire anything by hand ever again.
It will also have its own authentication (among other brilliant features) & I will make it _very_ robust & interference free. You're welcome. =^/.~=
- [ ] Fix up Player Controls.
  - Currently, whenever you leave your locomotive's cabin, you still have full control of your locommotive,
  & there is no way to turn this off. I will fix this up by bringing in the ability to use Remote Control Mode.
  I don't know how I'm gonna do this just yet. But, I'll cross that bridge when I get there.
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
