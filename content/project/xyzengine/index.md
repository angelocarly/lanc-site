---
title: "Xyzengine"
date: 2017-10-04T14:59:05+02:00
description: "A voxel engine written in Java using the LibGDX game development library."
cover: "/img/xyzengine/world.png"
---

A game engine written in Java using the [LibGDX](https://libgdx.badlogicgames.com) game development library.

I really enjoyed tinkering with graphics in high school. So when I had some free time during my Java Programming lessons in school I tried to develop a small game engine. I didn't really set a goal for it, but wanted to be able to render voxels and integrate shadows/lighting and physics. Which, after lots of debugging, I was able to achieve in the end.

The finished product is an engine written using LibGDX in Java. It support directional light, physics using JBullet and a destructible terrain.
![worldimage](images/world.png)

The physics required some thinking. You can't just add every single block in the scene as a collidable cube.
For example, this scene is about 32 blocks high, 256 blocks wide and 256 blocks in length. If unoptimized, the physics engine would have to check 32*256*256 = 2097152 different instances of cubes. Not really achievable for my shitty laptop at the time.

To remedy this, I used a greedy meshing algorithm with the help of [this great writeup on 0fps.net](https://0fps.net/2012/06/30/meshing-in-a-minecraft-game/).
A greedy meshing algorithm basically tries to combine as much cubes in a single cube. Which makes it possible to combine all the cubes in the scene into way less bigger cubes. You can see this in the following screenshot which shows all the physics objects in the scene.
![worldimage](images/world_wire.png)

The better physics system allowed for some fun sandbox sessions.
![worldimage](images/physics.png)

You can view the source code or try this engine here: 
- [Github repo](https://github.com/angelocarly/xyzEngine)  
- [Binaries](https://github.com/angelocarly/xyzEngine/releases)
