---
title: 3 - Recommended Project Setup
---

Once you are in a new project, I recommend these next steps:
Folder Structure, New Map, New Classes, Defaults.

1. **Folder Structure**
a. Open the Content Drawer, right click in open space and create a new folder.
b. Create the following folders in the same structure:

```
Content/
└── GameName/
    ├── Maps/
    ├── Core/
    ├── UI/
    └── Art/
```

2. **New Map**
Open the Maps Folder, right click and create a new level. Call it what you want.

![[MapA.png]]

3. **New Classes**
**a. New GameMode**

Open the Core Folder, right click and create a new **Blueprint Class.**

Select New **Game Mode Base**

![[GameModeBase.png]]

Call it what you want, but all blueprints should have **BP_** prefix.

![[NewGameModeBase.png]]

**b. New Character**

Create a new folder in the Core Folder called Player

```
Content/
└── GameName/
    ├── Core/
	     ├── ***Player***/
```

Then inside the Player folder, create two new Blueprint Classes.
- Player Controller
- Character
- 
![[PlayerCharacterController.png]]

Call them what you want, but Blueprints should have **BP_** prefix.

![[CharacterControllerBlueprints.png]]

4. Defaults

Go to the project settings.
Go to Maps/Modes

Change defaults to reflect your new blueprints.
- Default GameMode -> Your **BP_MyGameMode**
- Default Pawn Class -> Your **BP_Player**
- Default Player Controller Class -> Your **BP_PlayerController**

Then Change Map Defaults to reflect your new map.
- Editor Startup Map -> Your Map
- Game Default Map -> Your Map

![[ProjectDefaults.png]]
