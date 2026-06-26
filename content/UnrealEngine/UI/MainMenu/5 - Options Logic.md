---
title: 5 - Options Logic
---
#### Back Button
- Change the back button to a variable, give it the name `BTN_Back` then goto the Graph.
- Add this logic:

![[Pasted image 20260626162638.png]]  

#### Combo Box
- Change The Combobox to a variable, give it the name `DropDown_Graphics` and go to the graph
- While `DropDown_Graphics` is selected, add the `On Selection Changed` event from the details.
- Add this logic below:  
![[Pasted image 20260626165617.png]]  

- Now add a string variable called `SettingsMap`. Change its type to a Map
![[Pasted image 20260626165703.png]]  
- Make sure we're mapping String -> Integer and then compile.
- In the `Details` panel, add four values as below:  
![[Pasted image 20260626165758.png]]  

- Then Drag the `SettingsMap` variable into the graph, and get a `Find` node from it.
- Make the logic below:  
![[Pasted image 20260626165907.png]]  
