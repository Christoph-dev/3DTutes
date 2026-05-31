---
title: Runtime Virtual Textures
---
This is the setup for RVT with grass cards.
### Enable
1. Project Settings -> Rendering -> Virtual Textures
2. Tick Enable Virtual Texture Support
3. Restart Project

### Create RVT Asset
1. Right click in content browser and Create Runtime Virtual Texture.
2. Optional - Open the RVT and set the content to what you'll blend (like base colour).

### Add RVT Volume to level
1. In the Quick-Add menu, search for RVT volume and add to level.
2. Assign the RVT in details
3. In the details, set the bounds align actor to the Landscape and hit Set Bounds

### Add Virtual Texture to Terrain
1. Click Landscape
2. Add an element to 'Draw in Virtual Textures' in details.
3. Assign RVT

### Add RVT to material
1. Open grass card material
2. Add a Runtime Virtual Texture Sample node.
3. In the details of this node, assign the RVT
4. Plug base colour into output. Or see below for a stylised setup:
![[RVT.png]]

### RVT Output
1. Go to the Landscape Material
2. Add a Runtime Virtual Texture Output node.
3. Plug the terrain materials base colour into the RVT node.

Test, should be working.
