---
title: 1 - BP Interfaces
---
BP Interfaces are a way of broadcasting actions, and are an alternative to casting.

### 1 - Creating a hittable interface
*This interface will be used by objects that can be hit by the player*

- Inside the `Core` folder, right click inside the  `content browser` and search for `Blueprint Interface`
- Create it and call it `BPI_Hittable`, then open it
- Call the function inside the interface `OnHit`
- In the `Details` panel, click the small plus to add an `Input` variable
- Call the new input variable `Instigator` and change its type to an `Actor`
- Save and close the interface.

