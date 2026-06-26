---
title: 2 - Menu Logic
---

#### Opening Main Menu Widget
- Since we made a `Map_MainMenu Level`, we should open the widget via the `Level Blueprint`
- Open the `Level Blueprint` by following the images instruction:
![[Pasted image 20260626124401.png]]  

- Add a `Create Widget` node, and select WBP_MainMenu
- Then build the rest of this logic:  
![[Pasted image 20260626131855.png]]  
#### Button variables
- To use our buttons in in `WBP_MainMenu`, they need to be stored as variables.
- For each button, Change their name and tick the `Is Variable` checkbox.
	- BTN_Play
	- BTN_Options
	- BTN_Quit  
![[Pasted image 20260626123817.png]]  

#### Constructor / Destructor

*Constructors are run during widget creation, destructors are run during widget destruction.*
- Now look to the top right and move over from `Designer` to `Graph`.
- Build this logic below:  
![[Pasted image 20260626132031.png]]  
#### Play Game, Quit Game
- Click on `BTN_Play` in the list of variables, and then in the `Details` panel bottom left, add a `On Clicked` event.
- Add the logic below:  
![[Pasted image 20260626134939.png]]  

- Then for Quit game, click the `BTN_Quit` variable and add its clicked event and build the logic below:  
![[Pasted image 20260626135051.png]]  

