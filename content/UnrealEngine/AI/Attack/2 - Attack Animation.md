---
title: 2 - Attack Animation
---
*Add the [Dino Attack](/UnrealEngine/assets/Anim_Dino_Attack.fbx) animation into your Dino folder*

- Open the new animation and modify its Rate to preference. You should do this for walk/run also.
- Go to `\Dino`, right click the Anim_Dino_Attack asset and then Create -> Create Anim Montage
- Open up BP_Dino and add this one `Play Anim Montage` node to the DoAttack that we already made previously.  
![[AI_Attack1.png]]

- Then go into the `ABP_Dino` animation blueprint
- Add a `DefaultSlot` in between the Blendspace and the Outpot pose. THis is where the Montage gets played.  
![[Anim_Mont.png]]