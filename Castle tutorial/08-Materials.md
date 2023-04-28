# Materials

Let's make a new map, but first we save our assets.
New folder in Content folder, should be next to Starter Content.
Call it MyStuff.
To create a level, we can rightclick anywhere when inside the folder and select level, but instead
we're going to use a template level.
We're going to go to file and then New level and then basic.

This is nice, almost nothing, just the lighting settings and the ground.

The grid will be troublesome for the material so we will disable it using show and then uncheck grid.
we're also going to axis z-y and in the middle hover left click inwards to scale down the ground to a little ground.
Now it's quite tiny, don't forget to hit j to get in scale mode.
Another possibility is to use the numbers, 1 1 1 in every axis.
A nice little plate.

We're going to get a bunch of new assets, but these are not in the starter content.
Go to settings in the asset drawer, and check Engine > Content > EngineMeshes > SM_MatPreviewMesh_01
You can find it more easily by searching the name.

Then we create a post process volume, affect the entire world by details > Post process volume settings > Infinite extent (Unbound)
Then Lens > Exposure > Metering mode needs to be checked and set to manual. We set the value to 10.5
Make sure Lit > game settings is check on.
So there are lots of materials in All > Content > StarterContent > Materials.
To apply a material to a surface, just drag and drop it on top of the desired surface.
