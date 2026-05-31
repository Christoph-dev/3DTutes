---
title: Game Programming
---
This section covers some of the theory behind game programming.

___
## Math Foundations

### 1. The coordinate system
Unreal describes positions with three numbers: X, Y, Z

X = Forward  
Y = Right  
Z = Up  

The default unit in unreal is centimeters. So a value of 100 means 1 metre. A typical door is around 200 tall.

### 2. What is a vector?
A typical vector is just three numbers (X, Y, Z). It can mean two different things:

- A point in space - "The chest is at (500, 200, 0)"  
- A direction with length - "Move by (0, 0, 100)" *ie. 1 metre straight up*  

#### Common Vector Operations

| Usage                    | Operation                                                                                                                                                                                              | Example                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| **Distance** from A to B | Subtract                                                                                                                                                                                               | (200, 300, 100) - (1000, 300, 100) <br>= (700, 0, 0)                                           |
| **Length**               | Pythagorean Theorem<br>$$\sqrt{x^2 + y^2 + z^2}$$                                                                                                                                                      | V = (1, 2, 2) $$\|V\| = \sqrt{1^2 + 2^2 + 2^2} = 3$$                                           |
| **Normalisation** <br>   | Divide each element by the Length<br>- Makes length exactly 1.                                                                                                                                         | V = (1, 2, 2), \|V\| = 3<br>$$\hat{V} = (\frac{1}{3}, \frac{2}{3}, \frac{2}{3})$$<br>          |
| **Dot Product**<br><br>  | Sum-product of each element of two vectors.<br>$$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z$$<br>*- Parallel Direction = 0*<br>*- Perpendicular Direction = 1*<br>*- Opposite Direction = -1* | a = (1, 0, 0)<br>b = (0, 1, 0)<br>$$\hat{a} \cdot \hat{b} = (1)(0) + (0)(1) + (0)(0) = 0$$<br> |

### 3. Space: World, Local, Relative

World Space - The position within the whole level.  
Local/Relative Space - The position in relation to a parent object. A cup on a table keeps its local position if the table is moved, assuming its parented to the table.

### 4. Transforms

Location/Translation = Where  
Rotation = Its orientation, aka Pitch, Yaw, Roll.  
Scale = How big.  
___
## Blueprints

Unreal Engine's visual scripting - you build logic by wiring nodes instead of typing code.

A Blueprint is a class.  
A class is a reusable template.  
When you drag a blueprint into a level, you create an instance of it.  One "Door" blueprint can become a hundred actual doors, each with its own instance. Edit the blueprint and they all change.

#### Events
Code doesn't just run top-to-bottom. It also runs in response to events - things that happen:
- BeginPlay - Fires once when the game starts.  
- Tick - fires every single frame  
- Input/Output events - fire when the player presses a key, or two things touch etc.  

#### Wires
- White wires control the order of actions - "do this, then that"  
- Coloured data wires carry values - A number, true/false, a vector. Each colour is a different type of data.  

White = When, Coloured = What.

#### Delta Time

Frames don't all take the same amount of time. Delta time is the time since the last frame. If you want something to move at a steady space regardless of the players frame rate, you multiply the movement by delta time. It's the difference between:  
- Moves 10cm per frame (Dependant on frame rate)
- Moves 10cm per second (Delta time, smooth, fair across hardware)
___
### Materials

A material decides how a surface looks - its colour, glossiness, bumpiness. Under the hood its a shader: A small program the graphics card runs for every pixel on the screen.

#### PBR - Physically Based Rendering

Modern materials describe sufraces the way the real world does, using a few key inputs:

- **Base Colour** - The underlying colour.  
- **Metallic** - Is it metal or not?  
- **Roughness** - Is it dull or is it polished?  
- **Normal** - Fakes small bumps and dents without extra geometry.  

#### Textures and UVs

A texture is an image - a grid of coloured dots (Pixels). To wrap a flat image around a 3D Model, the model carries UV coordinates.: A map laid out in a 0-1 square that says "This part of the image goes on that part of the surface".

A useful bit of light math: **Multiply the UVs to tile a texture.** Multiply by 4 and the texture repeats 4 times - great for tiled textures like bricks and wood.

Things in materials are secretly vectors:  
- **Colour** is a vector - RGB is basically XYZ.  
- **Normal maps** store directions, not colours. 
___
## Landscapes
A landscape is Unreal's tool for big outdoor terrain - hills, valleys, mountains.

#### Heightmaps
Terrain is a flat grid of points pushed up or down by a heightmap - a greyscale image where white = high and black = low.

#### Performance
Landscapes are enormous, so Unreal shows lower-detail versions in the distance to keep things fast (this is called **LOD**, level of detail)

___
## AI
Game AI usually isn't intelligence, its decision-making. The pawn follows rules about what to do and when.

#### State Machine.
In a state machine, A character is always in exactly one **state** (Idle, Patrol, Chase, Attack), and **transitions** move it between them when conditions are met. "If I see the player, switch from Patrol to Chase."

#### Behaviour Tree
A behaviour tree works differently, instead of asking "What state am I locked in?" It asks, every tick, "From top to bottom, whats the most important thing i can do right now?". Behaviours are arranged as a tree and read top to bottom based on priority.

#### State Tree
A **State Tree** is a modern blend of a state machine and a behaviour tree. You define **states**, the **tasks** each state runs (like "move to this point"), and the **conditions** that move between them. It's a tidy way to answer "what am I doing right now, and what would make me do something else?"

