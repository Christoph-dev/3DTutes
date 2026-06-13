---
title: 1 - Chase and Attack
---
This tutorial builds on from Patrol AND Character Actions, which you should complete first.
### 1 - Aggressive State
- Open the AI Actor BP, BP_Dino.
- Add a boolean variable `Aggressive`. Default value of `False`
- Go to `Class Settings` and add the implemented interface `BPI Hittable`
	- *This is the same one we used for the tree.*
- Then add the `Event` into the event graph `OnHit`
- Add a new variable called `HostileTowards`
	- Set its type to `Actor`
- Then build this logic:  
![[AI_2.png]]  

### 2 - Modify Patrol State
- Go to the `ST_Dino` state tree we build in Patrol.
- Create a new state called `Patrol`
- Make `Patrol` a parent of `Find, Move, Wait`  
![[AI_6.png]]

- Then add a `Combat` State
- In `Patrol`, add a `Transition`
	- Change Trigger to `On Tick`
	- Change Transition To, to `Combat`
	- Set Priority to `Normal`
	- Add a `Bool Compare Condition` to this transition
		- Change `Left` to `Actor.Aggressive`
		- Change `Right` to `True  
	![[AI_8.png]]  

- Now add a second transition  
	- Set its `Transition To`, to `Find`

### 3 - AI Attack Logic
- Go into `\Core` and create a blueprint interface called `BPI_Attack`
- Change the function name to DoAttack
- Go to the AI BP, `BP_Dino`
- Go to Class Settings
	- Add the interface BPI_Attack to implemented interfaces
- Add a `Box Collision` component to `BP_Dino`.
	- Set its Box Extent to `200, 200, 64`
	- Call it `AttackBox`
- Now in the `Event Graph`, Call the event `DoAttack` from the BP Interface
- Build the logic below:  
![[AI_4.png]]  
*Now the dino can attack, but the player cant be hit*

#### Allowing the player to be hit
- Go to BP_Player
- Go to Class Settings
- Add the Hittable Interface to Implemented Interfaces
- Build the logic below:  
![[Pasted image 20260613231821.png|509]]  
*This is just for testing, we'll make it better in the next section*

### 4 - Attack helpers
*We need to make some State tree conditions and tasks to help our tree*

- Inside of the `\Dino` folder, create a new blueprint.
	- Look for `StateTreeCondition` and create it, call it `STC_PlayerInRange`
		- Open it and add three variables, and put them all in the category `Input`
			- `AttackInRange` -> Float
			- `SelfActor` -> Actor
			- `HostileActor` -> Actor
		- Then build the logic below in `STC_PlayerInRange`  
![[AI_10.png]]  

- Inside of the `\Dino` folder again, create another blueprint
	- Look for StateTreeTask and create it, call it STT_FindHostile
	- Open it and add two variables:
		- `HostileActor` -> Actor, category = Input
		- `Location` -> Vector, category = Output
	- Then build the logic below:  
![[AI_12.png]]  

- Inside of the `\Dino` folder one more time, create another another blueprint
	- Look for StateTreeTask and create it, call it STT_DoAttack
	- Open it and add one variable:
		- `Actor` -> Actor
	- Then build this logic below:  
![[AI_16.png]]  
### 5 - Chase Player
- Inside of the `Combat` state, add two states called `Attack` and `ChasePlayer`
- Inside of `Attack`, add two states: `MeleeAttack` and `Wait`
- Inside of `ChasePlayer`, add two states: `FindPlayer` and `Move`

- `Combat State`
	- Add a Bool Compare `Enter Condition`
		- Set Left to `Actor.Aggressive`
		- Set Right to True
	- Add a Transition
		- On `State Completed` -> Transition to `Next State`  
![[AI_24.png]]  

**!IMPORTANT**
- *We need an attack range on our BP_Dino, go into it and add a float variable AttackRange and set it to 200*

- Attack State
	- Add a STC_PlayerInRange `Enter Condition`, the one we created earlier.
		- Attack Range -> Actor.AttackRange
		- Self Actor -> Actor
		- Hostile Actor -> Actor.HostileTowards
	- Add a Transition
		- On State Completed -> Transition to `Next State`  
![[AI_22.png]]  

- ChasePlayer State
	- Add a Transition
		- Trigger -> On Tick
		- Transition -> Attack
		- Priority -> High
		- Add a condition STC_PlayerInRange
			- Attack Range -> Actor.AttackRange
			- SelfActor -> Actor
			- HostileActor -> Actor.HostileTowards
	- Add another Transition
		- State Completed -> FindPlayer  
![[AI_20.png]]  

- FindPlayer State
	- Create a Global Parameter inside the State tree and call it `HostileLocation`
	- Add a task STT_FindHostile
		- HostileActor -> ActorHostileTowards
		- Location -> Parameters.HostileLocation
	- Add a Transition
		- On State Completed -> Next State  
![[AI_26.png]]  

- Move State
	- Add a MoveTo Task
		- Destination -> Parameters.HostileLocation
	- Add a Transition
		- On State Completed -> Attack  
![[AI_28.png]]  
### 6 - Attack Player

- MeleeAttack State
	- Add a task STT_DoAttack
		- Actor -> Actor
	- Add a Transition
		- On State Completed -> Next State  
![[AI_30.png]]  
- Wait State
	- Add a task Delay
		- Set duration to 2.5 and random deviation to 0.5
	- Add a Transition
		- On State Completed -> Attack  
![[AI_32.png]]  
**The Final State Tree**  
![[AI_18.png]]  