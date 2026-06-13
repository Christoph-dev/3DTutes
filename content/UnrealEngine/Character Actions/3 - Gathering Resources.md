---
title: 3 - Gathering Resources
---
### 1 - Preparing Looting
*Before we make the loot, the player needs an inventory and a way to detect loot*
#### Loot Interface
- In core, create a new `Blueprint Interface` called `BPI_Loot`.
- Change the functions name inside the interface to `GainLoot`
- Add two inputs to `Gainloot`
	- Change the firsts name to `Loot`, and its type to a `String`
	- Change the seconds name to `Amount` and set its type to `Integer`
- Compile, save and close.

#### Using the interface on the Player
- Go to the `BP_Player` blueprint
- Go to `Class Settings`
- Add the interface to the implemented interfaces section.
- Create a variable called Inventory
	- Set its type to `String`
	- Set its Container Type to a `Map`
	- Set the right value to `integer`  
![[Interfaces10.png]]  
*Maps are key -> value pairs.* Good for inventories.

- Compile and then add three default values to `Inventory`
	- Wood -> 0
	- Stone -> 0
	- Ore -> 0
![[Interfaces11.png]]  
*Anything can be added to the inventory, but we'll start with these 3*

- Now create  the `GainLoot` **event** inside BP_Player
- Add the logic below:  
![[Interfaces12.png]]  

### 2 - Looting
#### Building the Wood Collectable BP
- Create a Resources folder in the Art folder.
- Import [this pack](/UnrealEngine/assets/SM_ResourcePickups.fbx) of pickup resources into the Resources folder.
	- *Feel free to make a flat brown material for it*
- Create an `Actor` blueprint called `BP_WoodPickup`
- Add a `Static Mesh` component and assign the wood model.
- Add a `RotatingMovement` component
- Add a `Sphere Collision` component
	- Adjust the collision so it aligns with the mesh.
#### Logic for the Wood Collectable BP
- Go into the Event Graph of `BP_WoodPickup`
- Click on `Sphere` and scroll down to its events. Click the plus on the `On Component Begin Overlap` event.
- Add the logic below:  
![[interfaces13.png]]  

#### Modify the tree to drop resources
*You can put this per hit or at the end when the tree falls*
- Go to `BP_HittableTree`
- Add this logic to the fall down. *Or just add to each hit on the tree*
![[interfaces14.png]]