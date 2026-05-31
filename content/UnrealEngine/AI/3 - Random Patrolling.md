---
title: 3 - Random Patrolling
---
1. Open ST_Dino
2. Click Add State, call it 'Find'
### Find

**Radius Parameter**
1. Add a Parameter by clicking the blue plus.
2. Rename the Parameter to Radius
3. Change its type to a Float
4. Set the Radius to about 1000  
5. ![[AI16.png]]  

**Find Task**
1. Add a task by clicking the cyan plus
2. Click our STT_FindRandomLocation task.
3. Bind the Radius Parameter by following this:  
4. ![[AI13.png]]  

5. Bind Actor to Actor in the same way
6. Then click on the bind for OutLocation and promote to a global parameter.  ![[AI14.png]]  

**Find Transition**
1. Click on the pink plus to add a transition.
2. Set it to Transition to the Next State.  
![[AI15.png]]  

## Move
1. Add a new state, name it Move.
2. Add a task - Move To
3. Change the binding of the Destination to the OutLocation global parameter.  
![[AI17.png]]

4. Add a transition, transition to Next State

### Wait
1. Add a new state, name it  Wait
2. Add a task - Delay Task
3. Set it to whatever you like, I'll use 3 seconds, deviation of 2.
4. Leave the Transition to go back to root, no need to change.  
![[AI18.png]]

Compile and Save.

![[AI19.png]]
