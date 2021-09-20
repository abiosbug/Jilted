

## Avoidance

### Rangefinder Grouping

#### Rangefinder hardware layout

![Rangefinder Layout](assets/rangefinderlayout.png)

```
                        []         
  
 []   []    []    []    []    []    []    []    []
  
 []   []    []    []    []    []    []    []    []
               []    []    []    []
 []   []    []                      []    []    []
                   []   []   []
 []   []    []   []            []   []    []    []
                   []        []
 []   []    []          []          []    []    []
               []    []    []    []
 []   []    []    []    []    []    []    []    []
   
 []   []    []    []    []    []    []    []    []
    
                        []    
```

#### Layout
```
__|  |  |  |  |__
_____/  |  \_____
_____  .-.  _____
_____  .-.  _____
__   \  |  /   __
  |  |  |  |  |  
```

#### Name Groups
```
                          TT         

  TRC   TRC   TR    TR    TT    TL    TL    TLC   TLC     

  TRC   TRC   TR    TR    TB    TL    TL    TLC   TLC
                 TR    TB    TB    TL
  TR    TR    TR                      TL    TL    TL 
                     C    D    C 
  RR    RR    RL   RL            LR   LR    LL    LL 
                     C         C 
  RB    RB    BR          C           BL    BL    BL 
                 BR    BT    BT    BL
  BRC   BRC   BR    BR    BT    BL    BL    BLC   BLC

  BRC   BRC   BR    BR    BB    BL    BL    BLC   BLC

                          BB    
```

#### Radar Display

```
[][][][][]
[][][][][]
[][][][][]
[][][][][]
[][][][][]
```

```
TRC TR  TT  TL  TLC
TR  TR  TB  TL  TL
RR  RL  C   LR  LL
BR  BR  BT  BL  BL
BRC BR  BB  BL  BLC
```

## YOLOL ROOM
```
|\     /|
| \   / |
|L | | R|
| /   \ |
|/     \|
```

### LEFT
```
-------------------------------------------------------------
|  ===B===  |  ===A===  |  ===M===  |  -------  | main      | 
|  ===B===  |  ===A===  |  ===M===  |  -------  | memory    | 
|  ===B===  |  ===A===  |  ===M===  |  -------  | switch    | 
| spares B  | spares A  | spares M  |   space   | waypoints |  
-------------------------------------------------------------
| main      | nomnom    | flow      | approach  | delta     |
| memory    | drillbit  | navlight  | scanner   | heading   |
| switch    | ===A===   | ===A===   | ===A===   | memory    |
|   ship    |  dances   | utility   |  mining   | waypoints |
-------------------------------------------------------------
| info      | main      | 3in1      | main      |  ===M===  |
| singular  | memory    | isan nav  | output    |  ===M===  |
| memory    | switch    | memory    | delta     |  ===M===  |
| jilted    | lasers    | compass   | compass   | waypoints |
-------------------------------------------------------------
| main      |    TRC    |   auto    |  ===M===  |  ===A===  |
| memory    |    TLC    |  memory   |  ===M===  |  ===A===  |
| brake     |    BRC    |  ===A===  |  ===M===  |  ===A===  |
| avoidance | avoidance | navcas    | compass   | spares    |
-------------------------------------------------------------
| abbrev    | safety    |  CENTER   |   LEFT    |    TRL    |
| FCU trans | boot      |    TOP    |   RIGHT   |    BRC    |
|     |     |         O |  BOTTOM   |    TLC    |    BLC    |
| m-relays  | emergency | avoidance | avoidance | avoidance |
-------------------------------------------------------------
```

### RIGHT
```
-------------------------------------------------------------
| ._______. | ._______. | ._______. | ._______. |  ===A===  |
| |       | | |       | | |       | | |       | |  ===A===  |
| |_______| | |_______| | |_______| | |_______| |  ===A===  |
|  # 1      | # 2       | # 3       | # 4       | spares    |
-------------------------------------------------------------
|  ===B===  |   GENS    |   HOVER   |   MAIN    |  STATUS   |
|  ===B===  |  TURTLE   |   ping    |  DEFAULTS |  MEMORY   |
|  ===B===  |  ===A===  |  ===A===  |   MEMORY  |  TIMERS   |
| spares    | power     | utility   | fix       | info      |
-------------------------------------------------------------
|   DIST    |    CH1    |    CH4    |   CROSS   |  -------  |
|  CENTER   |    CH2    |    CH5    |   RADAR   |  -------  |
|    TT     |    CH3    |  DISPLAY  |   RADAR   |  -------  |
| radar     | crosshair | crosshair | radar mem | space     |
-------------------------------------------------------------
|    TB     |  flight   |     RL    |    LL     |    BR     |
|    BB     |  control  |     RR    |    TR     |    BL     |
|    BT     |     +     |     LR    |    TL     |    BLC    |
| radar     | transpond | radar     | radar     | radar     |
-------------------------------------------------------------
|    TRC    |                       | Distance  | switches  | 
|    BLC    | MAIN FLIGHT COMPUTER  |           | 9 spares  | 
|    BRC    |                       |           |     |     | 
| radar     |                       | bios      | m-relays  | 
-------------------------------------------------------------
```
