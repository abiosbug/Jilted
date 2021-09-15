## Device fields

Overview of all device fields used in the setup

| field        | map | default | device      | info                      |
| -----        | --- | ------- | ----------- | ------------------------- |
| :AlwaysOn    |     | 1       |warn button  | State for always enabled devices
| :AlwaysOn    |     | 1       |lid button   | State for always enabled devices
| :MBC         |     | 1       |button       | Color of the :AlwaysOn lid button, based on INSZ
| :Boot        |     | 1       |twist handle | Kickstart ship after power loss
| :NoPilot     |     | 1       |button       | Blink state of the :AlwaysOn button
| :AAS         |     | 0       |button       | Asteroid Avoidance Switch |
| :AS          |     | 0       |button       | Approach Switch           |
| :LS          |     | 0       |button       | Laser Switch              |
| :LD          |     | 0       |button       | LaserDance Switch         |
| :Seat        |     | 0       |button       | Pilot chair slider open   |
| :Distance    | :DS |         |rangefinder | Central rangefinder     |
| :AUTO        |     | 0       | button | Autopilot
| :PP          |     |         | rangefinder | Pilot chair rangefinder |
| :Approach    |     | 0       | button |
| :Cruise      |     | 100     | button |
| :RangeFinderDistance | :RD | 995 | rangefinder |
| :Laser       |     | 0       | laser |
| :Mi          |     | 0       | collector |
| :TS          |     | 0       | button | Turtle switch, override turtle mode with lever value
| :TMO         |     | 0       | lever  | Turtle mode override value: controls the centering speed of Pitch & Yaw
| :Fix         |     | 1       | button | 
| :FLOW        |     | 0       | switch |
| :FSC         |     | 3       | switch color |
| :UDC         |     | 100     | lever | Up Down Cruise
| :RLC         |     | 100     | lever | Rightleft Cruise
| :HM          |     | 0       | button | HoverMode
| :RFHD        |     |         | rangefinder | HoverMode down rangefinders
| :HotSpot     |     | 25      | lever | maximum opening angle of laser turrets
| :DaN         |     | 0       | button | next dance
| :DaP         |     | 0       | button | previous dance
| :navlights   |     | 0       | button | ship exterior nav lights
| :NLP         |     | 0       | bulbe | navlights Port
| :NLS         |     | 0       | bulbe | navlights Starboard
| :NLT         |     | 0       | bulbe | navlights Top
| :Transponder |     | -1      | switch |
| :OVR         |     | 0       | button | Override safety 
| :LaserDance  |     | ""      | text panel |
| :scan        |     | ""      | textpanel |
| :OL          |     | 0       | scanner | Active 
| :OI          |     | 0       | scanner | Indexa
| :OR          |     | 0       | scanner | ScanRresults 
| :OM          |     | ""      | scanner | Material 
| :OV          |     | 0       | scanner | Volume 
| :OS          |     | 0       | scanner | Scan 
| :____        |     | ""      | text panel | Radar crosshair
| :Timers      |     | ""      | text panel |
| :Refuel      |     | 0       | button | Opens the rod doors


### Levers

| field | info                |
| ----- | ------------------- |
| :YM   | Max YAW value       |
| :YN   | Min YAW value       |
| :PM   | Max PITCH value     |
| :PN   | Min PITCH value     |


### Rangefinders

| field | # | info                |
| ----- | - | ------------------- |
| :RFC  | 5 | Center              |
| :RFTT | 2 | Top Top             |
| :RFTB | 4 | Top Bottom          |
| :RFBB | 2 | Bottom Bottom       |
| :RFBT | 4 | Bottom Top          |
| :RFR  | 3 | Right               |
| :RFL  | 3 | Left                |
| :RFTL | 5 | Top Left            |
| :RFTLC| 3 | Top Left Center     |
| :RFTR | 5 | Top Right           |
| :RFTRC| 3 | Top Right Corner    |
| :RFBL | 5 | Bottom Left         |
| :RFBLC| 3 | Bottom Left Corner  |
| :RFBR | 5 | Bottom Right        |
| :RFBRC| 3 | Bottom Right Corner |
| :HMD  | 4 | 
