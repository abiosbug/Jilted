# YOLOL
There's a lot of YOLOL involved (+50 chips), and one of the main bottlenecks is the processing speed.
If you need speed, you want your code to run on a single line on an individual chip.  Most operations can be done on the Basic YOLOL chip, but for repurposing purposes, I'm only using Advanced chips.

I've grouped the YOLOL sections per logical feature and color coded them.  I try to keep everything together inside the designated racks: both the script checking for a switch or button, as well as the actual script and possible memory chips.

Files names `.split.yolol` are expected to have each line run on a separate chip for maximum performance.  However you can split them up as you see fit if performance is less critical.  
Files named `.mem.yml` are supposed to be put on memory chips.  
relayed.yml contains the Memory Relay mapping values.

## Development - YODK
If you've ever wondered how the ISAN code was made, look no further, because if you take YOLOL serious, you want to consider the [YODK framework][1].  This allows for less limited coding and will transpile to compact and performant YOLOL, allowing you to focus on functionality instead of limitations.  Have a look at their project to get you started.  I'm still in the process to test all this out myself and will provide more info here as I discover it myself.  I mean, they even have a (limited) testing framework so you can validate your scripts without ever needing to paste it in-game.

## Memory Relays
Memory Relays can be used in the same network to rename variables.  This allows for YOLOL-free display label adjustments as well as concise scripted FCU manipulations without having custom keybinds.  You'll need 2 memory chips as well and place them in the relay slots.  Wire both cable connections to the network as well.  Note the arrows indicating which chip will pass on its value to the other chip as the relays work in a single direction.  The fields are mapped in order, so 1st field of the input chip maps to the 1st field on the output chip.

Example Propellant calculation: instead of having to sum up and set the total stored propellant to eg `:Propellant`, you can use the Memory Relay to map `:GasNetworkStoredResource` to `:Propellant`.  
Example FCU manipulation: you want `:roll=100` in a script to roll right and `:FCURotationalRoll` is just too long to fit on your line, you map `:roll` to `:FCURotationalRoll` and be done with it!

## Global variables
A lot of advanced scripts use global variables (the ones with a leading `:`) to share values between different chips.  Basic scripts use them too to listen for buttons or enable devices.  
🐛 There is no memory locking  or variable checking in YOLOL so you can easily overwrite existing variables, causing unintented behaviour (naming clashes), aka bugs.  
⚠️ Using global variables in YOLOL that don't exist, causes the line to be silently ignored.  _ISAN for example takes advantage of this to detect a Quad or Mono setup._  
There are 2 ways to create a global variable:
1. assign it to a TextPanel, Button, Switch or Device instance
2. add it to a memory chip

## Displays - BLUE

### Info
### Fuel / Propellant
### Statusd
### Timers
### Radar
### Crosshair

## Navigation - PURPLE

### Ping
### Waypoints
### Compass

## Avoidance - GREEN

## Mining - ORANGE

### Approach
### Turtle
### Pulse
### Generator

## Laser - RED

### LaserDance
### NomNom
### DrillBit

## Safety - BLACK

### Pilot Present

[1]: https://github.com/dbaumgarten/yodk
