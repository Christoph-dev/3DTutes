---
title: 3 - AI Health
---
#### Dino can now die
- Go to BP_Dino and add a integer variable called `HP`
- Set it to a reasonable value, such as `10`
- Add this logic to the end of the already existing OnHit event.
![[AI_GetHit.png]]  
*We'll make this more interesting in another section, and make a death animation.*


#### Better OnHit interaction
*You can add this to BP_Dino but also BP_Player, so getting hit can be felt*

- Add this to the OnHit event  
![[OnHitLogic.png]]  

#### Better Death interaction (Dinos)

- Add this logic before the `Destroy Actor` node.
- You will need to make an adequate timeline for it, which you should be able to do now if you followed the previous steps up until this.  
![[FallOverOnDeath.png]]  