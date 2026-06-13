---
title: 2 - Random Location Task
---
1. Right click in the content browser and add a Blueprint class.
2. Search for StateTreeTaskBlueprintBase and add this blueprint.
3. Call it STT_FindRandomLocation and open it up.  
![[public/UnrealEngine/assets/AI_11.png]]

4. On the right, create 3 variables:
	- Name: Radius, Type: Float
	- Name: Actor, Type: Actor
	- Name: OutLocation, Type: Vector
5. Click the open eye (to make them public) for each.  
![[public/UnrealEngine/assets/AI_13.png]]

6. Click each variable, and in the details on the right, give each one a category:
	- Radius, Category = Input
	- Actor, Category = Input
	- OutLocation, Category = Output  
![[public/UnrealEngine/assets/AI_15.png]]

7. In the graph, search for Get Navigation System
8. Drag from Get Navigation System and search for Get Random Reachable Point In Radius  
![[public/UnrealEngine/assets/AI_17.png]]

9. Drag the Actor variable into the graph from the left.
10. Drag From Actor and search for Get Actor Location
11. Drag in the Radius variable.
12. Plug Actor Location and Radius into the Get Random Reachable Point in Radius node.  
![[public/UnrealEngine/assets/AI_19.png]]

13. Drag from Random Location and Set OutLocation.  
![[public/UnrealEngine/assets/AI_21.png]]


14. Search for and add an EnterState event.
15. Search for and ad a FinishTask node.
16. Connect as below, then compile and save.  
![[public/UnrealEngine/assets/AI_23.png]]

