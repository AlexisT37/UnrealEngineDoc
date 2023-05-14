# Megascan

It's a huge library of free assets for Unreal Engine, and we're going to get assets for our project here.
First let's reset the texture of the landscape to the default by using the counter clockwise arrow on the material selection on the landscape details.
Note that if we can't select anything in the Outliner, it's probably because we are still in the landscape mode.
Now we're back to checker.
Now we're going to add a post process volume into the map
Add > Volumes > PostProcessVolume
Then we go to its details to set the exposure to manual
Metering Mode > Manual in the dropdown after checking the parameter
Exposure Compensation we check it, but there are no effects so far.
Then we check Post Processing volume settings >  infinite expand (Unbound).
We now can set the exposure compensation to 10, (was set to 11.5 in the video)
Now we are going to add elements, in the Main Viewport, select Add > Quixel Bridge.
This takes us to the menu for the assets.
Now let's look for the Mossy forest Rock.
We had to go and link our account with unreal engine, but now it's done and I can simply drag and drop items from the bridge. It's really awsome ^^
There are two new folders in our content drawer now, and they are named
Megascans
and
MSPresets
The Megascans folder contains the internal components for the mossy rock, like the static mesh, the normal map, the texture.
As for MSPresets, it contains all the masterMaterials that Megascan uses.
If we go to the rock material, we can see that it is not a material on its own but an instance material. If we go to edit it, we can see its corresponding master material.
Details > Parent > and its parent is called M_MS_Default_Fuzz_Material.
Now we are going to go over all the characteristics for this material because we are going to use them consistently.
Let's start by undocking the material so we can see what happens in real time when we change the material settings.
We're going to start with albedo (Witcher vibes)
Details > 01 - Albedo
The Albedo Tint is disabled by default, but if we check it and use the color picker, then we can change the color of the rock at will.
