---
title: 1 - Balloons
---
![[Pasted image 20260627175558.png|313]]
#### BP_Balloon Setup
- In your `\Core` folder, create an Actor blueprint called `BP_Balloon`
- Add a `Sphere` Component, size it close to a balloon.
	- Move it up so its base sits just above origin.
	- Enable `Simulate Physics`
	- Set its `Mass` to 1 kg.

- Add a `Cable` Component, call it `String`
	- Make the `String` a child of `Sphere`
	- Move the Cable so its attached to the base of the `Sphere`
	- Increase `Solver Iterations` to about `10`
	- Set End Location to `[0, 0, 0]`

- Add a Physics Constraint, make sure its parented to nothing.
	- Set all Linear Limits to `Limited`
	- Set Limit to 300
	- Set Component Name 2 to `Sphere`

#### Constant Upward Force
- Go to the Event Graph of `BP_Balloon`, make an Event Tick node
- Drag in the sphere component
- Drag from `Sphere` and Add Force
- Set the force to `[0, 0, 1000]`  
![[Pasted image 20260626214954.png]]  
#### Attach Balloon Event
- Create a Custom Event inside the BP - Call it `AttachComponenet`
- Drag in the `Physics Constraint` Component
- Drag from `Physics Constaint` and `Set Constraint Components`
- Drag `Component1` onto the `CustomEvent` node to make it an input.
- Drag `BoneName1` onto the `CustomEvent` node to make it another input.
- Drag `Sphere` in, and set it as `Component2`  
![[Pasted image 20260626215449.png]]  

- Now drag in `Cable`
- Drag from `Cable`, `Set Attach End to Component`
- Drag from `Cable` again, `Set End Location`
- Build logic Below:  
![[Pasted image 20260626220156.png]]  

#### Input Action
- Make an input action inside `\Core\Player\Inputs` called IA_Balloon
- Go into `IMC_FPS` and add a mapping
- Assign the mapping to IA_Balloon
- Give it a key like `B`

- Then go into `BP_Player` and add this input action event to the Event Graph  
![[Pasted image 20260626214234.png]]  

*continued...*
![[Pasted image 20260626214255.png]]  

