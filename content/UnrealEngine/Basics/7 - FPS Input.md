---
title: 7 - FPS Input
---
1. Go to the **Core/Player/** Folder that we created in [[3 - Project Setup|Step 3]]  
2. Create a new folder called **Input**  
3. In the **Input** folder, create a Input Mapping Context called IMC_FPS  
![](https://d1iv7db44yhgxn.cloudfront.net/documentation/images/d0923212-114f-40ee-8d97-d564edc2ec80/image_5.png)

4. Then right click and create three **Input Actions**, found in the same area.  
Name them:  
- IA_Look  
- IA_Movement  
- IA_Jump  
![[FPSInput2.png]]

4. Open IA_Look and set its **Value Type** to Axis2D. Save and close it.  
![[FPSInput1.png]]

5. Open IA_Movement and set its **Value Type** to Axis2D as well. Save and close it.  
6. Then open IMC_FPS and add a Mapping Profile  
7. Then add three mappings one at a time. 
- IA_Jump  
- IA_Look  
- IA_Movement  
![[FPSInput3.png]]

8. Expand IA_Jump and click the keyboard icon, then press Spacebar to assign it.
9. Expand IA_Look and assign Mouse XY 2D-Axis.
10. Expand IA_Movement and assign four keys: W, S, A, D, by clicking the plus and the keyboard icon each time.  
![[FPSInput4.png]]

11.  Expand S and add a Negate Modifier
12. Expand A and add a Negate and Swizzle Modifiers
13. Expand D and add a Swizzle Modifier  
![[FPSInput5.png]]

14. Save and Close the IMC_FPS.
15. Head to /Core/Player/, open the **BP_PlayerController** Blueprint.  
![[public/UnrealEngine/assets/FPSInput6.png]]

*Click this if it pops up*  
![[FPSInput7.png]]

16. In the Graph Editor, Search for an add this node:  
![[FPSInput8.png]]

17. Drag from the RIGHT of **EnhancedInputLocalPlayerSubsystem** and search for **Add Mapping Context**
18. Drag from the LEFT of **EnhancedInputLocalPlayerSubsystem** and **get a ref to Self**  
![[FPSInput21.png]]

19. Set the mapping context from the dropdown
20. Connect the White Execution Pin as below:  
![[FPSInput22.png]]

21. Compile, Save and close the **PlayerController** BP.
22. Open up the **BP_Player** Blueprint.
![[FPSInput11.png]]

22. Open up the content drawer and drag the three Input Actions *IA_Look, IA_Movement, IA_Jump* into the graph editor.
![[FPSInput12.png]]

23. Build the Jump logic by adding a **Jump** and **Stop Jumping** Node to the Graph Editor. Connect them to Triggered and Completed respectfully.  
![[FPSInput14.png]]

24. Build the Look logic by adding a **Add Controller Pitch** and **Add Controller Yaw** nodes to the Graph Editor.
25. Right Click the Action Value on the IA_Look Input, and split it to X and Y.  
![[FPSInput15.png]]

26. Connect X to Camera Yaw. Multiply the Camera Pitch by -1 and connect it to Camera Pitch.
27. Then connect as below:  
![[FPSInput16.png]]

28. For IA_Movement, first find and add these two nodes:
- Get Actor Right Vector
- Get Actor Forward Vector  
![[FPSInput17.png]]

28. Then find and add two **Add Movement Input** nodes.  
29. Finally, connect them up as below:  
*If you need to bend wires, double click them*  
![[FPSInput18.png]]

30. Now we need a camera for the player to see through. Click on viewport in top left, then add a camera.  
![[FPSInput19.png]]

31. Click the camera and adjust it in the viewport if needed by dragging the arrows.  
32. Then in the details of the Camera, Turn on Pawn Control Rotation.  
![[FPSInput23.png]]

33. Compile and Save BP_Player.
34. Now go to your level and add a **Player Start**  
![[FPSInput20.png]]

35. Change the Mode to Selection if needed, and move the player start somewhere meaningful. Then test out your Player Controls!