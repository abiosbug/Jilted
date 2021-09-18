# Jilted
_Collection of adjustments done to the Jilted_  
⚠️ This is still very much work in progress, dont expect to be able to just copy paste yolol and have what's listed below ⚠️  
_A lot of information is still missing, screenshots, part lists, build info, field names, etc  
I started this repo for debugging YOLOL as it became unwieldly in-game: no search, no syntax checks, nothing to debug complicated setups.  Having all yolol code, memory variables and relay variables in one folder, working with vscode and the yolol extension has already helped a lot!_

## Purpose & Background
This repo serves as a blueprint to keep track of the things I adjusted during my work on the Jilted.  
This ship, designed by Sun-cy, under the Singularity company, inspired me to add all the features I expect from a luxurious mining ship.

## Functional Mods

### T2/T3 Drive Train
The Jilted comes default with a T2 Fuel chamber and generator setup, with enhancers.  All triangle thrusters, used as manoever thrusters, are T2 as well.  The box thrusters are T1 as the ship already goes 150 m/s empty.  That didn't stop me from changing them to T2 as well, I even added T3 nozzles for that extra punch.

### Ninja Turtle mode
Enabling the Mining mode activates the ships Turtle mode by default, ideal for dense asteroid fields or stations.  When the lasers are activte, your movements slow down even more so you can do even more precise movements.

### Pilot chair
I was bothered by the way the cockpit gets in your view, especially after finishing up on an asteroid I found it hard to find the next one.  So I added a slider, bolted to the frame, so the pilot chair is bolted to the moving arm.  Since the chair requires power, I used a duct slider to allow it to remain powered, even whilst sliding.

### PID controlled Approach
Approaching an object based on a Rangefinder measurement requires a constant feedback loop, as your ship behaves different to FCU inputs depending on its load.  A PID loop is the perfect match to tackle this problem, so you can have a self-correcting system that works within the given variation boundaries.  Added 5 other central rangefinders to the Distance calculation so you have it easier keeping the asteroid locked on.

### Hover Mode
The Jilted comes equipped with a warp core to allow for moon mining trips, so I added 4 rangefinders on the bottom of the ship and a slider to adjust the desired hover height.  Uses the same PID controlled system as the Approach feature

### YOLOL room
I wanted to have a very accessible YOLOL setup as I intend to tinker a lot with it.  I reorganized the racks so there are plenty of chips in sockets as well as color coded the racks by functionality.  I also added plenty of spare chips, racks and sockets so I'd never be shy of empty chips or space to work on the next YOLOL thing.  

### Laser Dance
I spent a lot of time clearing my inventory when mining, and it felt like a huge time waste to be busy with the inventory UI whilst the ship lasers are not hitting anything.  I already saw videos of people adjusting the laser angles and turret rotations so I added a Laser Dance feature, allowing the lasers to move in efficient patterns automatically.  I added 2 different dances and room for more to experiment with.  By default, the Jilted has a Pulse laser script that will never drain the batteries.  Enabling the Laser Dance will disable this pulse and will eventually drain your batteries.

#### NomNom
The NomNom dance was the first one I created. It is just slowly opening up and closing the laser beams, resembling a chewing motion, hence the name NomNom.  I added just a little roll as well, depening on how much opening the laser beams currently have.

#### DrillBit
The second Dance makes your ship go roll as fast as possible, whilst slowly opening up the laser beams, slowing down the laser opening movement the greater the angle is.  The idea was to arrive at an asteroid, center the ship, enable the drill and have it carve out the asteroid from the center outwards to the edge.

### Asteroid Avoidance System and Radar
Whilst the Jilted has alread a best-in-class avoidance system in place, I reworked the resolution of the rangefinders to have 15 unique zones of detection next to the central distance rangefinder.  The motivation was to have some kind of radar display that would show which zone is triggered when the avoidance kicks in.  I also added a counter that counts every avoidance the script has done.  When AAS is off, you'll have a basic cross on the radar.  With AAS enabled, all 15 zones are reporting back to the display in 9 groups.

### Compass
The amazing people of the Collaborative Yolol Learning Open Network have created a [compass module][1], see for yourself what this OP thing can do!

### Status screen
A text panel showing you if you're in SafeZone, whether you can place a station, the amount of durability errors if any and your current ship strength factor.
Another text panel with your estimated Time Left values for Propellant and Fuel

### 30 Waypoint System
Any navigation feature works better when you can select and store waypoints without having to use the U tool, so I added the 30 waypoint system from [Archeageo][2]

### Autopilot and Navigation
Select a stored waypoint, hit the button and watch the ship align itself and take off on its own.  Will constantly check it's heading along the way and correct when needed.  Still in it's early development as the alignment feature is currently very slow.  Displays Deltas and opening/closing angles as well.  Using the compass first to align yourself manually and only then hitting the button works best for now.  Uses the excellent [NAVCAS setup][3] for the navigation part (NAV)

### Pilot Presence Detection
When using automated lasers, you don't want to risk being caught by one so a rangefinder pointed at the pilot works wonders.  Leave the seat and the lasers turn off, that's all it does.  Ofcourse you can add functionality as you see fit.  Includes an override button so you can still risk it if needed, eg. when testing your new Laser Dance script.

### QOL
- Flow In Both Out switch
- Automatic laser (de)activation based on distance
- 5 additional rangefinders for distance calculation, so more margin of error when aiming

## Cosmetics
- Colored hardpoints for the Rangefinders array as well as for the resource bridges and laser equipment.
- Headlight and ship lights
- Reorganized controls to accomodate for the moving chair and extra panels
- More batteries so you can dance longer and for perfect balance
- YOLOL free Fuel and Propellant calculation with Memory Relays
- Added Fuel racks instead of bolted rods
- Adjustable YOLOL rack labels & color coded chips
- Plenty of YOLOL sockets to tinker with whilst flying
- Modest attempt to lightshow using random rangefinders when not in Avoidance mode
- Glass protection for all thrusters, fuel rods & propellant tanks



## Credits

I couldn't have even started this project without the help, kind assistance, information and helping hands of a lot of people.

- Singularity Starbase Community - [discord][4]
  Special thanks to the following people (in no particular order)
  * Singularity
  * Sun-cy
  * CeramicTurtle
  * DeathPanda
  * Icehawks
  * Chucknorris
  * Eminent
  * Xhaos
  * so many more, for the listening, the sharing, the helping


- Collaborative Yolol Learning Open Network - [discord][5] - [github][6]
  * Firestar - Compass & Math lib - [gitlab][7]
  
- [Starbase Discord][8]
- DerPfandadler Material scanner - [github][9]
- Archeageo Waypoint system - [github][10]
- Fixerid NAVCAS - [github][3]



[1]: https://gitlab.com/Firestar99/yolol/-/tree/master/src/compass
[2]: https://github.com/Archaegeo/Starbase/tree/main/ISAN-Waypoint%20System
[3]: https://github.com/fixerid/sb-projects
[4]: https://discord.gg/Qtj95qwZ6J
[5]: https://discord.gg/chkwznZbjW
[6]: https://github.com/CylonSB/
[7]: https://gitlab.com/Firestar99/yolol
[8]: https://discord.gg/xwe8CZXB3c
[9]: https://github.com/DerPfandadler
[10]: https://github.com/Archaegeo/Starbase

[]: 