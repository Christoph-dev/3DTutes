---
title: 1 - Importing & Setup
---


You'll first need a skeletal mesh and animations. This tutorial will be using a dinosaur pack found [here](/UnrealEngine/assets/Dino.zip).

1. Create a **Dino** folder inside the Art folder. (*assuming you follow same conventions as I*)
2. Find the **SK_Dino.fbx** asset and drag it into this folder.
3. When the FBX importer pops up, deselect **Import Materials** and then hit import.
4. Find the **Dino_Face.fbx** asset and drag it into this folder, just hit import.
5. Finally drag the three animation files into the content browser and hit import.  
![[Anim1.png]]


### Making a material  
This model doesn't have textures, so you can make a simple flat material in its place.  

1. In the same dino folder, create two materials, one for the dino body and one for the face features.
2. Feel free to make them what you want, but I'm using flat white and flat black.  
![[Anim2.png]]

3. Then open up the SK_Dinosaur and Dino_Face and set these materials in the details panel.

### Making the character blueprint
The dino will use the Character Blueprint because it provides walking and more by default.

1. In the same dino folder, right click and create a blueprint class and choose Character Blueprint.
2. Name it BP_Dino
3. Open up the BP_Dino, select the Mesh component  
![[Anim3.png]]

4. Then in the details panel on the right, change the Skeletal Mesh Asset to our SK_Dino.
5. Set the Location of the Dino Mesh to **\[0, 0, -88]**  
![[Anim4.png]]

6. Select the Capsule component and in the details panel on the right, change the radius of the capsule to 60.