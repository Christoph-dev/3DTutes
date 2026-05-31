---
title: 4 - Animation BP
---
The Animation Blueprint is we will feed our characters actual speed into the blendspace.

1. In the same dino folder, right click and create an Animation Blueprint called ABP_Dino
	- Select the Dino skeleton when prompted
2. Open it up and go to the EventGraph tab.  
![[Anim12.png]]

3. Search for and create these nodes:
	- Begin Play
	- Cast to BP_Dino
4. Connect as below, and then right click **'As BP Dino' and promote to variable**.  
![[Anim13.png]]

5. Then in a different section create these nodes:
	- Right click and search for **Get As BP_Dino**
	- Drag from BP_Dino and **Get Character Movement**
	- Drag from Character Movement and **Get Velocity**
	- Drag from Velocity and get **XY Length**
	- Drag from XY Length and **promote to parameter**. *(then call it speed)*  
![[Anim14.png]]

6. Then add these final nodes and connect together:
	- Right click and search for **Event Blueprint Update Animation**
	- Right click and search for **? Is Valid**
7. Connect execution pins as below:  
![[Anim15.png]]


8. Now go back over to the AnimGraph tab
9. Right click and add a State Machine called **IdleToRun.**
10. Connect it to the Output Pose and then double click on **IdleToRun**.  
![[Anim18.png]]

11. Drag across Entry and add a State called **IdleToRun**.  
![[Anim17.png|342]]

12. Double click on **IdleToRun**.
13. Right click and add out blend space from previous section. BS_IdleToRun.
14. Drag in our Speed variable from our variable list on the right
15. Connect Speed to Speed.  
![[Anim16.png]]

16. Save and Compile.
17. Go back to our original character blueprint BP_Dino.
18. Click on the Mesh component and then in the details, set our animation blueprint class:  
![[Anim19.png]]

19. If you character is now idling, everything is working.