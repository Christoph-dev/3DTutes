---
title: 1 - Menu Design
---
#### Main Menu Level
- Create a new level called `Map_MainMenu` inside of the Maps folder.
- Open up this level
#### UI Folder
If you don't have one yet, create a UI folder inside your game folder:

Content/
└── GameName\
    ├── Maps\
    ├── Core\
    ├── Art\
    └── UI\   <----

#### Main Menu Widget
- Inside of the `UI` folder, right click and create a Widget Blueprint.  
![[Pasted image 20260626114642.png]]  

- When the prompt shows up, choose `User Widget`  
- Call the widget `WBP_MainMenu`
- Open the widget.

#### Main Menu UI
- In the Palette section (*top left*), search for and add a `Horizontal Box` by dragging it into the viewport
- Then add a `Spacer` to the Horizontal Box
- Now add a `Vertical Box` to the Horizontal Box
- Finally add another `Spacer` to the Horizontal Box  
![[Pasted image 20260626121105.png]]  

- Shift select the `Spacer`, `Vertical Box` and `Spacer`.
- In the details panel on the right, click `Fill` so all three are affected.  
![[Pasted image 20260626121206.png]]  

- Now inside of the Vertical Box, add these in this order:
	- Spacer
	- Text
	- Spacer
	- Button
	- Spacer
	- Button
	- Spacer
	- Button
	- Spacer
- Then select all of them and click `Fill` in the details panel.  
![[Pasted image 20260626121653.png]]  

![[Pasted image 20260626121714.png]]  

- Click on the Text Block and change its alignment in the `Details` panel, so that it is centered.
- Change the Text Blocks `Text` in the details to what you want.
	- You can expand the Font to change it also.

- Our buttons need text also, so add a `Text` to each of them also by dragging `Text` on top of the buttons.
- Change the texts on the buttons to:
	- Play Game
	- Options
	- Quit  
![[Pasted image 20260626122144.png]]  

![[Pasted image 20260626122155.png]]  

- You can modify and design these buttons further as you choose, such as background, font size, and spacer padding.

