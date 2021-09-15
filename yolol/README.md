# YOLOL
There's a lot of YOLOL involved (+50 chips), and one of the main bottlenecks is the processing speed.
If you need speed, you want your code to run on a single line on an individual chip.  Most operations can be done on the Basic YOLOL chip, but for repurposing purposes, I'm only using Advanced chips.

I've grouped the YOLOL sections per logical feature and color coded them.  I try to keep everything together inside the designated racks: both the script checking for a switch or button, as well as the actual script and possible memory chips.

Files names `.split.yolol` are expected to have each line run on a separate chip for maximum performance.  However you can split them up as you see fit if performance is less critical.  
Files named `.mem.yml` are supposed to be put on memory chips.  
`relayed.yml` contains the Memory Relay mapping values.

## Overview

\* = Advanced YOLOL chip  
+n = Memory chip

| feature    | # chips    | category   |
| -------    | ---------- | ---------- |
| ship       | 2+1        | ship       |.
| boot       | 1          | ship       |.
| fix        | 1+2        | ship       |.
| flow       | 1          | ship       |.
| info       | 1          | ship       |.
| navlights  | 1          | ship       |.
| hover      | 1*         | ship       |.
| relays     | 0+6        | ship       |.
| ping       | 1          | status     |.
| radar      | 25+3       | status     |.
| status     | 1+1        | status     |.
| timers     | 1*         | status     |.
| safety     | 1*         | safety     |.
| generators | 1          | mining     |.
| approach   | 1*         | mining     |.
| scanner    | 1*         | mining     |.
| turtle     | 1          | mining     |.
| ISAN       | 1*         | navigation |.
| avoidance  | 19+1       | navigation |.
| compass    | 4*+3       | navigation |.
| autopilot  | 1*         | navigation |.
| waypoints  | 4*+3       | navigation |.
| laserdance | 4*+1       | laser      |.
|            |            |            |
| totals     | 19* 58 +20 |            |


## Development - YODK
If you've ever wondered how the ISAN code was made, look no further, because if you take YOLOL serious, you want to consider the [YODK framework][1].  This allows for less limited coding and will transpile to compact and performant YOLOL, allowing you to focus on functionality instead of limitations.  Have a look at their project to get you started.  I'm still in the process to test all this out myself and will provide more info here as I discover it myself.  I mean, they even have a (limited) testing framework so you can validate your scripts without ever needing to paste it in-game.

## Memory Relays
Memory Relays can be used in the same network to rename variables.  This allows for YOLOL-free display label adjustments as well as concise scripted FCU manipulations without having custom keybinds.  You'll need 2 memory chips as well and place them in the relay slots.  Wire both cable connections to the network as well.  Note the arrows indicating which chip will pass on its value to the other chip as the relays work in a single direction.  The fields are mapped in order, so 1st field of the input chip maps to the 1st field on the output chip.  See the [Memory Mapping table](relayed.md)

Example Propellant calculation: instead of having to sum up and set the total stored propellant to eg `:Propellant`, you can use the Memory Relay to map `:GasNetworkStoredResource` to `:Propellant`.  
Example FCU manipulation: you want `:roll=100` in a script to roll right and `:FCURotationalRoll` is just too long to fit on your line, you map `:roll` to `:FCURotationalRoll` and be done with it!  

## Global variables
A lot of advanced scripts use global variables (the ones with a leading `:`) to share values between different chips.  Basic scripts use them too to listen for buttons or enable devices.  
🐛 There is no memory locking  or variable checking in YOLOL so you can easily overwrite existing variables, causing unintented behaviour (naming clashes), aka bugs.  
⚠️ Using global variables in YOLOL that don't exist, causes the line to be silently ignored.  _ISAN for example takes advantage of this to detect a Quad or Mono setup._  
⚠️ Initial values do matter for string concatenation! eg. If you let it default as 0 and start adding strings to it, it will remain 0.  This applies to Memory Relay variables as well.

There are 2 ways to create a global variable:
1. assign it to a TextPanel, Button, Switch or Device instance
2. add it to a memory chip

### Ship

- [Ship](ship.yolol) General ship logic
  roup front rangefinders - automatic laser activation
  - [ship-switches.yolol] Less critical switches 

### Displays - BLUE

- [Info](info.yolol)
- [Status](status.yolol)
- [Radar](radar.yolol)
- [Crosshair](crosshair.yolol)

## Navigation - PURPLE

- [Ping](ping.yolol)
- Waypoints:
  - [Archeageo repo][3]
  - [Waypoints](waypoints.yolol)
    Dropped the included ISAN as the ISAN Navigator bundle already calculates the needed values
- Compass
  - The amazing Compass bundle from FireStar [compass.yolol] using his first released version v1.0  
    Requires 3 rangefinders placed front back right.  Rotated the display 90 deg clockwise to counteract the bottom placement.  
    Uses an insanely efficient ISAN (10 lines!) for all 3 receivers at once :mindblown:  
    Comes with additional rotational matrix export via vars `:ix :iy :iz :jx :jy :jz :kx :ky :kz`  
    Allows for efficient manual orientation before starting the autopilot
- Navigation:
  - ISAN Navigator bundle [ISAN-navigator_bundle.yolol]
    Comes with latest ISAN and needs only 2 yolol chips to run ISAN and a waypoint addon for 16 waypoints. Not using the waypoint addon.  
  - NAVCAS bundle, only using the NAV part [nav-only.yolol]
    Tries to pitch and yaw the ship towards the target, but in an inefficient way to work around the game limitations (in short, the direction readings go crazy as soon as you start moving).  After your ship has aligned itself within 30 degrees, it will take off and keep correcting itself whilst in flight and stop when within 1km of your target.   
    Applied the following translation matrix and dropped the 3 custom ISAN scripts:  
    |        | NAVCAS | Compass | Matrix |
    | :----  | ------ | ------- | ------ |
    | FRONT  | a & at | kf & kt |        |
    | F X    | xa     | fx      | jx     |
    | F Y    | ya     | fy      | jy     |
    | F Z    | za     | fz      | jz     |
    | BACK   | j & jt | ke & kt |        |
    | B X    | xj     | ex      | ix     |
    | B Y    | yj     | ey      | iy     |
    | B Z    | zj     | ez      | iz     |
    | DOWN   | a & at | kf & kt |        |
    | F X    | xk     | gx      | kx     |
    | F Y    | yk     | gy      | ky     |
    | F Z    | zk     | gz      | kz     |


## Avoidance - GREEN

- [Enable](avoidance-enable.yolol)
- [Scripts](avoidance.split.yml)
- [Memory](avoidance.mem.yml)

## Mining - ORANGE

- [Approach](approach.yolol)
- [Turtle](turtle.yolol)
- [Pulse](pulse.yolol)
- [Scanner](scanner.yolol)
  Based off the [excellent scanner script][5] from DerPfandadler, adjusted the variable names to be prefixed
- [Generator](generator.yolol)

## Laser - RED

- [LaserDance](laserdance.yolol)
- [LaserDance NomNom](laserdance-nomnom.yolol)
- [LaserDance DrillBit](laserdance-drillbit.yolol)

## Safety - BLACK

- [Safety](safety.yolol)

[1]: https://github.com/dbaumgarten/yodk
[2]: https://gitlab.com/Firestar99/yolol/-/tree/master/src/compass
[3]: https://github.com/Archaegeo/Starbase/tree/main/ISAN-Waypoint%20System
[4]: https://github.com/fixerid/sb-projects
[5]: https://github.com/DerPfandadler/Pfandadler-YOLOL