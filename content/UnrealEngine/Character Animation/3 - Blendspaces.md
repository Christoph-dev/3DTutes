---
title: 3 - Blendspaces
---
For our character to transition from idle -> walk -> run in a smooth way, we need a Blendspace.

1. In the same Dino folder, right click and create a BlendSpace  
![[Anim9.png]]

2. When prompted, select our Dino skeleton and then call it BS_IdleToRun
3.  Open up the blend space, and on the left - expand the Horizontal Axis and set its values to:
	- Name: Speed
	- Max Axis Value: 600  
![[Anim10.png]]

4. Now in the timeline at the bottom, drag in our three animations:
	- Idle to bottom left
	- Walk to bottom center
	- Run to bottom right  
![[Anim11.png]]

5. To test, hold control and click around in the timeline to see the dinosaur blend between animations.
6. Save