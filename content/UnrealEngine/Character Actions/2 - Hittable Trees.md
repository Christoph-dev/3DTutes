---
title: 2 - Hittable Trees
---
### 1 - Making a tree hittable.
*This will allow the tree to be mined by the player*
#### Creating the asset and assigning the interface  
- Inside the `Core` folder, right click inside the `content browser` and create an `Actor Blueprint`
- Call it `BP_HittableTree` and open it.
- Add a `Static Mesh` component, call it `Tree` and change its `Static Mesh` to a static mesh such as the Palm Tree from the list of assets.
- Click on `Class Settings` at the top and then find the `Details` panel.
- In the `Interfaces` area, click on the `Add` drop down and click `BPI_Hittable`

#### Creating the Event logic
- In `BP_HittableTree`, create a variable called `Hitpoints` and change its type to `Integer`.
- Inside the `Event Graph` of `BP_HittableTree`, right click and search for `OnHit`, add the event which should derive from the interface.
- Build the below logic:  
![[Interfaces1.png]]

- Then right click and search for `Add Timeline...` and create it.
- Double click the timeline, click `+Track`.
- Rename the `Track` to `Shudder`.
- Set the Length to 0.24
- Right click in the timeline and add a key.
	- Set the keys `Time` to 0.06, and its `Value` to 1.0
- Add another key.
	- Set the second keys `Time` to 0.18 and its `Value` to -1.0
- Add a final key
	- Set the third keys `Time to 0.24` and its `Valu` to 0.
- Right click every key and set their interpolation to `Auto`.  
![[Interfaces2.png]]

- Now go back to the Event Graph and make logic from the `True` output of the branch we created earlier.  
![[Interfaces3.png]]

- Now create another timeline by searching `Add Timeline...`
- Open this timeline, add a track of length 2.0.
- Set the tracks name to `FallDown`
- Right click in the timeline to add these three keys:
	- `Time` 0.0, `Value` 0.0
	- `Time` 1.25, `Value` 30
	- `Time` 2.0, `Value` 90
- Right click each key and change the interpolation to `Auto`.  
![[Interfaces4.png]]

- Go back into the event graph and build the following logic from the `False` output of the branch node we created earlier.  
![[Interfaces5.png]]

- Finally to make the tree disapear just add these to the 'Finished' output of the timeline.  
![[Interfaces9.png]]



### 2 - Adding the action to the Player.

#### Creating the components
- In the BP_Player blueprint, add a `Static Mesh` component.
- Name the static mesh `Tool` and make it a child of the `Camera`
- Set its Location and Rotation to be around the hand of the player.
- Add a `Sphere Collision` component and place it infront of the player
	- Set its radius to 32
	- Call it `InteractSphere`  
![[Interfaces6.png]]

- Then in the `Event Graph`, we need to save the initial transform information of the tool.  
![[Interfaces7.png]]

#### Making the Swing Event
- In the `Event Graph` of `BP_Player`, search for an add a `Custom Event`
	- Cal it `SwingTool`
- Then we need to build the logic below.  
![[Interfaces8.png]]

- **THE SWING TIMELINE
	- Add two Tracks, a float track `0To1` and an Event track `DoHit`
		- `0to1` needs `Length` of 0.35
			- Add a key of `Time` 0 and `Value` 0
			- Add a key of `Time` 0.1 and `Value` 1
			- Add a key of `Time` 0.35 and `Value` 0.
			- Then set all keys to `auto`.
		- DoHit just needs one key at `Time` 0.1.

#### Attack Input
- Go to the Core\Player\Input folder
- Create a input action called `IA_Swing`
- Go to the IMC_FPS Mapping Context
- Add a new mapping for IA_Strike
- Set the bound key to LMB
- Then goto BP_Player and build this logic:  
![[Interfaces22.png]]   


**Now try hitting a tree.**
*Any other actors that have the BPI Hittable interface will also work*
