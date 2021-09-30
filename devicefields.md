## Device fields

Overview of all device fields used in the setup
The map column indicates if the value is translated via memory relays  



| field        | map | default | device       | info                      |
| -----        | --- | ------- | -----------  | ------------------------- |
| :AlwaysOn    | :ON | 1       | warn button  | State for always enabled devices
| :AlwaysOn    | :ON | 1       | lid button   | State for always enabled devices
| :MBC         |     | 1       | button       | MainButtonColor of the lid button, based on INSZ
| :Boot        |     | 1       | twist handle | Start ship
| :NoPilot     |     | 1       | button       | Blink state of the :AlwaysOn warn button
| :AAS         |     | 0       | button       | Asteroid Avoidance Switch |
| :AS          |     | 0       | button       | Approach Switch           |
| :LS          |     | 0       | button       | Laser Switch              |
| :LD          |     | 0       | button       | LaserDance Switch         |
| :TA1         |     | -10     | turret       | Left Laser Turret Angle   |
| :TA2         |     | -10     | turret       | Top Laser Turret Angle    |
| :TA3         |     | -10     | turret       | Right Laser Turret Angle  |
| :Seat        |     | 0       | button       | Pilot chair slider open   |
| :RFDS        |     | 0       | rangefinder  | Central rangefinder distance |
| :Auto        |     | 0       | button       | Autopilot
| :Dest        |     | `\n\n\n    off` | text panel | Destination coordinates
| :DTW         |     | `\n\n\n    off` | text panel | Destination waypoint
| :Deltas      |     | `\n\n\n    off` | text panel | Waypoint deltas
| :Heading     |     | `\n\n\n    off` | text panel | Waypoint heading
| :PP          |     |         | rangefinder  | Pilot chair rangefinder |
| :Appr        |     | 0       | button | Enable automatic approach
| :Cruise      |     | 100     | button | Sticky forward
| :Home        |     | 0       | button | Set waypoint 1
| :Save        |     | 0       | button | Save current coordinates to current waypoint
| :RangeFinderDistance | :RD | 995 | rangefinder |
| :Laser       |     | 0       | laser | Laser Active state
| :Mi          |     | 0       | collector |
| :TS          |     | 0       | button | Manual turtle switch, override turtle mode with lever value
| :TMO         |     | 50      | lever  | Turtle mode override value: controls the centering speed of Pitch & Yaw 16 < :TMO < 100
| :Fix         |     | 0       | button | 
| :FLOW        |     | 0       | switch |
| :alignment%  | :e  | 0       | progress bar | shows the general alignment % from ISAN navigator
| :distancewp  | :f  | 0       | progress bar | shows the distance to target from ISAN navigator
| :FSC         |     | 3       | switch color | Allows changing switch lever color based on flow state
| :HM          |     | 0       | button | HoverMode
| :HD          |     | 15      | lever | Hover Distance, doubles as approach distance when not in hover mode |
| :RFHD        |     |         | rangefinder | HoverMode down rangefinders distance
| :HotSpot     |     | 10      | lever | opening angle of laser turrets
| :DaN         |     | 0       | button | next dance
| :DaP         |     | 0       | button | previous dance
| :NavLights   |     | 0       | button | ship exterior navigation lights
| :NLP         |     | 0       | bulbe | navlights Port
| :NLS         |     | 0       | bulbe | navlights Starboard
| :NLT         |     | 0       | bulbe | navlights Top
| :Transponder |     | -1      | switch |
| :OVR         |     | 0       | button | Override safety 
| :LaserDance  |     | ""      | text panel |
| :Turtle      |     | "\n\n\n    off" | text panel | Shows current turtle mode info
| :Scans       |     | ""      | textpanel | Scanner results output
| :OL          |     | 0       | scanner | Active 
| :OI          |     | 0       | scanner | Index
| :OX          |     | 0       | scanner | ScanResults
| :OM          |     | ""      | scanner | Material 
| :OV          |     | 0       | scanner | Volume 
| :OS          |     | 0       | scanner | Scan 
| :____        |     | ""      | text panel | Radar crosshair
| :TTI         |     | "booting timers" | default timer panel value
| :STI         |     | "booting status" | default timer panel value
| :NTI         |     | "booting navigation" | default timer panel value
| :RTI         |     | "booting radar" | default timer panel value
| :CTI         |     | "booting compass" | default timer panel value
| :WTI         |     | "booting waypoints" | default timer panel value
| :SCTI        |     | "booting scanner" | default timer panel value
| :Timers      |     | ""      | text panel |
| :Refuel      |     | 0       | button | Opens the rod doors
| :singular    |     | `\n    _-_    \n  //    \  \n\\\\\\\\\\\\n  \_  _//\n     -     \n` | text panel | Holds the Singularity logo ASCII
| :k           |     | ` Compass\n.         .\n.         .\n-    +    -\n.         .\n.        by\nFireStar99` | text panel

### FCU Levers

| field | info                |
| ----- | ------------------- |
| :YM   | Max YAW value       |
| :YN   | Min YAW value       |
| :PM   | Max PITCH value     |
| :PN   | Min PITCH value     |
| :UDC  | Up Down Cruise
| :RLC  | Rightleft Cruise


### Rangefinders

| field | # | info                |
| ----- | - | ------------------- |
| :RFC  | 0 | Distance of 5 center rangefinders |
| :RFC1 | 1 | on state center rf  |
| :RFC2 | 1 | on state center rf  |
| :RFC3 | 1 | on state center rf  |
| :RFC4 | 1 | on state center rf  |
| :RFC5 | 1 | on state center rf  |
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
| :HMD  | 4 | Hover Mode Down     |
