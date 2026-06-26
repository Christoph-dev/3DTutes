---
title: 4 - Options
---
#### Widget Setup
- Create a new widget blueprint inside `UI` called `WBP_Options`
- Open it and add a `Border`
	- Change the border `Brush Color` to whatever you like *(I chose black)
- Then add the same components we used in `WBP_MainMenu`:
	- Horizontal Box
	- Spacer
	- Vertical Box
	- Spacer  
![[Pasted image 20260626160002.png]]  
- Select all of them and click `Fill` in the Details panel.

#### Options Settings
- Then add these to the vertical box:
	- Spacer
	- Text
	- Spacer
	- Text
	- ComboBox (String)
	- Spacer
	- Text
	- Slider
	- Spacer
	- Text
	- Slider
	- Spacer
	- Button
	- Spacer
- Select all of them and click `Fill` in the Details panel.  
![[Pasted image 20260626160013.png]]  
![[Pasted image 20260626160027.png]]  

- Now modify the text of each text block:
	- First: `Options` *and change to Center Alignment*
	- Second: `Graphics:`
	- Third: `SFX:`
	- Fourth: `Music:`
- Add a text block to the button and modify it to becalled `Back`  
![[Pasted image 20260626160237.png]]  

#### Combo Box
- Click on the ComboBox and scroll down to the `Content` section in `Details`
- Add four `Options` elements.
- Rename them:
	- Epic
	- High
	- Medium
	- Low
- Set the `Selected Option` as Medium by default.
- Compile and save to see it work.