---
title: 2 - Grab Objects
---
*This tutorial allows you to grab physics based objects, Elder Scrolls style.*

#### Setup
- Go to BP_Player and ad a `Static Mesh` component, parented to Camera.
	- Call the static mesh `ObjectSlot`
- Now add a `Physics Constraint` Component, parented to `ObjectSlot`
	- Call it `GrabConstraint`  
![[Pasted image 20260627181648.png]]  
``
	- Set these settings to `GrabConstraint`:
		- Set all `Linear Limits` to `Free`
		- Set all `Angular Limits` to `Free`  
![[Pasted image 20260627184344.png]]  
		- Enable Linear Motor Positions
			- Set Strength to 1000
		- Enable Velocity Targets
			- Set Damping to 100
		- Change Angular Drive Mode to `Twist and Swing`
		- Enable Twist and Swing Target Orientation
			- Set Strength to 1000
		- Enable Twist and Swing Target Velocity
			- Set Damping to 100  
![[Pasted image 20260627184443.png]]    

``
	- Set `ObjectSlot`'s `Static Mesh` to a Sphere
		- Set `Hiden In Game` -> `True`
	- Change its `Collision Preset` to `Custom`
		- Set all to `Ignore`

#### Grab Input
- Add a new Input Action to `\Core\Player\Input` called `IA_Grab`
- Go into `IMC_FPS` and add IA_Grab as a mapping
	- Set its key to right click

#### BP_Player Logic
- Go into `BP_Player`
- Create the IA_Grab Event
- Add a variable called `HeldObject`, set its type to `Primitive Component`
- Add the logic below:  
![[Pasted image 20260627182424.png]]  
*continued...*  
![[Pasted image 20260627182442.png]]  