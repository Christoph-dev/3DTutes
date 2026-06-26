---
title: 3 - Pause Menu
---
*If you used the same logic as the previous section, the main menu can also be used as a pause menu.*


#### Input
- Add a new input action to \Core\Player\Input called `IA_Pause`
- Open up the input mapping context `IMC_FPS` *or whatever you called yours*
- Add a new mapping and assign `IA_Pause`
- Use a key that will work in editor such as `P` - *You can add ESC as well*  
![[Pasted image 20260626140321.png]]  

#### Assigning Pause Input
- Open up `BP_Player`
- Add the `IA_Pause` event
- Build the logic below:  
![[Pasted image 20260626140431.png]]  

Make sure to test.