

## Avoidance

### Rangefinder Grouping

#### Rangefinder hardware layout
```
                    []         

        []    []    []    []    []     

  []    []    []    []    []    []    []
           []    []    []    []
  []    []                      []    []
               []   []   []
  []    []   []            []   []    []
               []        []
  []    []          []          []    []
           []    []    []    []
  []    []    []    []    []    []    []

        []    []    []    []    []    

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

        TRC   TR    TT    TL    TLC     

  TRC   TRC   TR    TB    TL    TLC   TLC
           TR    TB    TB    TL
  TR    TR                      TL    TL
               C    D    C 
  R     R    R             L    L     L 
               C         C 
  RB    BR          C           BL    BL
           BR    BT    BT    BL
  BRC   BRC   BR    BT    BL    BLC   BLC
        BRC   BR    BB    BL    BLC    

                    BB    
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
| switch    | ===a===   | ===a===   | ===a===   | memory    |
|   ship    |  dances   | utility   |  mining   | waypoints |
-------------------------------------------------------------
| info      | main      | 3in1      | main      |  ===m===  |
| singular  | memory    | isan nav  | output    |  ===m===  |
| memory    | switch    | memory    | delta     |  ===m===  |
| jilted    | lasers    | compass   | compass   | waypoints |
-------------------------------------------------------------
| main      |    TRC    |   auto    |  ===M===  |   DIST    |
| memory    |    TLC    |  memory   |  ===M===  |  CENTER   |
| brake     |    BRC    |  ===A===  |  ===M===  |     T     |
| avoidance | avoidance | navcas    | compass   | avoidance |
-------------------------------------------------------------
| abbrev    | safety    |     R     |    TB     | top left  |
| FCU trans | boot      |     L     |    TOP    | bot right |
|     |     |         O |     TR    |    BT     | bot left  |
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
|    BLC    |     TL    |    DIST   |   CROSS   |    TOP    |
| CROSSHAIR |     BR    |   CENTER  |   RADAR   |    TB     |
|  ===B===  |     BL    |    TOP    |   DISTS   |   BOTTOM  |
| avoidance | power     | utility   | fix       | info      |
-------------------------------------------------------------
|   RIGHT   |     TL    |    DIST   |   CROSS   |    TOP    |
|   LEFT    |     BR    |   CENTER  |   RADAR   |    TB     |
|    TR     |     BL    |    TOP    |   DISTS   |   BOTTOM  |
| radar     | radar     | radar     | radar mem | radar d   |
-------------------------------------------------------------
|    TB     |  flight   |     BT    |    BR     |    TLC    |
|    B      |  control  |     TR    |    BL     |    BRC    |
|    BT     |     +     |     TL    |    TLC    |    BLC    |
| radar     | transpond | radar d   | radar d   | radar     |
-------------------------------------------------------------
|    TLC    |                       | Distance  | switches  | 
|    BRC    | MAIN FLIGHT COMPUTER  |           | 9 spares  | 
|    BLC    |                       |           |     |     | 
| radar     |                       | bios      | m-relays  | 
-------------------------------------------------------------
```
