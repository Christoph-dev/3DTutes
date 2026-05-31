---
title: 1 - StateTree Setup
---
In this lesson we're going to use the Dinosaur from the Character Animation for a simple random patrolling AI.

### Enable the Plugin
1. Go to Edit -> Plugins
2. Search for 'GameplayStateTree'
3. Enable and restart Unreal.

### Creating the Assets
1. Right click in our Dino folder and add a StateTree
2. Click StateTree AI Component
3. Call it ST_Dino

4. Right click in our Dino folder and add a Blueprint Class
5. Find AI Controller  
![[AI1.png]]

 6. Create it and call it "BP_DinoAIC"

### Setting up the AI Assets
 1. Open the BP_DinoAIC
 2. Add a StateTreeAI Component  
![[AI2.png]]

 3. In the details of the StateTreeAI Component, select ST_Dino
![[AI3.png]]

4. Now open up the State Tree ST_Dino
5. Set AI Controller Class to BP_DinoAIC
6. Set Context Actor Class to BP_Dino  
![[AI5.png]]


### Assigning AI to our Character
1. Open up BP_Dino
2. Make sure BP_Dino component is selected (the first one)
3. In the details search for PAWN
	- Set Auto Possess AI = Placed in World or Spawned
	- Set AI Controler Class = BP_DinoAIC  
![[AI4.png]]

4. Compile and Save.

