---
title: 9 - Materials
---
## Flat Material
*A Flat material just has colour, roughness and specular input.*

1. Go to your \Art\ folder, right click and create a Material called M_FlatGreen  
![[Materials1.png]]

2. Double click to open this Material.
	- *The brown node you can see is the Output Node*
3. Hold down 3 and click in space to create a Vector(RGB) node.
4. Double click on the Vector node to change the colour.
5. Then connect the output pin into the **Base Colour** of the Output Node.
	- *For a stylised look, just set roughness to 1 also*  
![[Materials2.png]]

6. Feel free to create other flat colours, it is a good way to block out a world.
7. To assign the Material to a Mesh, you can either:
a. Drag the material onto the mesh.
b. Or set the material in the details panel of the mesh.

## Textured Material
*This material has texture file inputs. We'll be making a brick Material*  
*You can download the resource pack [here](/UnrealEngine/assets/Resources.zip)*

1. Go to your \Art\ folder and create a Material called M_Brick.  
![[Materials3.png]]

1. Double click on the material.
2. Open up the content drawer and find your textures. Drag them all in
	- *I have _D, _N, _H, _R texture files.*
	- D = Diffuse (base colour)
	- N = Normal
	- H = Height
	- R = Roughness  
![[Materials4.png]]

1. Align and plug materials as per screenshot below:  
![[Materials5.png]]
*BumpOffset is its own node for a simple height map use. You can search for it and add it.*

1. Change preview object to Cube to see a realistic preview of the brick texture.  
![[Matrerials6.png]]
