---  
weight: 3  
---  

# Game Modes

In this section, we will explain each game mode available in <b>CloudsEvents</b> and their configuration.  

## General Configuration
There is a general configuration section for every game mode that must be set up.

<i>The location where players will spawn when joining the event (X,Y,Z,Yaw,Pitch).</i>  
```yaml title="Coordinates"  
  spawn-location: "0.5,70.0,0.5,0.0,0.0"  
```
<i>The two vertices of the spawn cage (X,Y,Z).</i>  
```yaml title="Cage Coordinates"  
  spawn-cage-pos1: "-5,60,-5"  
  spawn-cage-pos2: "5,65,5"  
```  

<i>The location where players will spawn when the event starts (X,Y,Z,Yaw,Pitch). To disable this (so players will not be teleported), type "disabled".</i> 
```yaml title="Game Spawn"  
  game-spawn-location: "0.5,60.0,0.5,0.0,0.0"  
```  

<i>The Y level for player death.</i>  
```yaml title="Player Death"  
  y-death: 50  
```  

## Color Party 

The <b>Color Party</b> game mode allows you and other players to play with colors. The game <b>randomly</b> selects a color, and you <b>must</b> stand on a block of that color. The last player to fall <b>wins</b>.  

=== "Before the Config"  
    Before configuring the mode, you’ll need to <b>build a map</b> for it.<br><br> 
    <b>How will you do it?</b><br> 
    To do it, you must build a map with a spawn cage and a colored platform below it, including all the colors available in Minecraft.<br>
    
    <i>For example:</i><br> 
    ![ColorPartyMap](https://i.imgur.com/RsDMrdn.png){ align=left }  

=== "After Building"  

    After building the map, we can configure the `mapConfig.yml`. In this case, the configuration will be explained <b>specifically for this game mode</b>.  

    <i>The two vertices of the game base (X,Y,Z).</i>  
    ```yaml title="Vertices of Game base"  
            game-base-pos1: "25,60,25"  
            game-base-pos2: "-25,60,-25"  
    ```  

    <i>The blocks used in the game base. Available blocks: wool, terracotta, concrete.</i>  
    ```yaml title="Color of blocks"  
            color-block: "wool"  
    ```  

    <i>The level from which PvP will be enabled. To disable it, type -1.</i>  
    ```yaml title="Level of PVP enabled"  
            pvp-level: 10  
    ```  

    <i>The PvP type. If multiple, separate them with `;;`</i>  
    : <i>HAND (fist combat)</i>
    : <i>SNOWBALL.</i>  
    ```yaml title="PVP type"  
            pvp-type: "HAND;;SNOWBALL"  
    ```  

    <i>The hotbar position for snowballs (1-9).</i> 
    ```yaml title="Snowball position"  
            snowball-hotbar: 9  
    ```  

    <i>Levels section (level: seconds).</i>  
    ```yaml title="Level countdown"  
            levels:  
              1: 5  
              3: 4  
              5: 3  
              10: 2  
    ```  

    And this is how you can configure the ColorParty game.  

## TimerSpleef  
The <b>TimerSpleef</b> mode consists of multiple platforms where, if a player touches a block, it changes color until it <b>disappears</b>. The last player to fall <b>wins</b>.  

=== "Before the Config"  
    Before configuring, as in ColorParty, you <b>must</b> build a map for this mode. There will be a spawn cage, but instead of a colored platform, there will be multiple platforms made of a specific block, stacked one below the other. For example:  
    ![TimerSpleefMap](https://i.imgur.com/rryGfk5.png){ align=left }  

=== "After Building"  
    <i>The blocks in the different levels. Use the server version Material API (level: "material") [For legacy versions, use Material:Data].</i>  
    ```yaml title="Blocks Level"  
            blocks-level:  
            0: "WOOL:0"  
            1: "WOOL:4"  
            2: "WOOL:1"  
            3: "WOOL:14"  
    ```  

    The seconds between each level.  
    ```yaml title="Seconds"  
            level-time: 5  
    ```  

## SumoFFA  
The SumoFFA mode consists of PvP without weapons. The last player to fall wins.  

=== "Before the Config"  
    Before configuring, as in the previous game modes, you need a map with a spawn cage and a platform below where players can fight. For example:  
    ![SumoFFAMap](https://i.imgur.com/WSsb7WU.png){ align=left }  

=== "After Building"  
    <i>In this mode, there is no specific configuration. Unlike the previous ones, you only need to fill in the general configuration.</i>