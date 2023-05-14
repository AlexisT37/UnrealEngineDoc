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
Now we need to be careful, because there doesn't seem to be a way to cancel changes to an asset, so we're going to make a copy of it. We need to remember to assign the material to the rock. It's ok though, if there is a problem then we can just delete the rock and delete the two folder and then get the rock again from the quickscan bridge.
Here I took the liberty to change the material because I want to practice not needlessly corrupting downloaded assets.
So I have a second material, duplicated from the first one, with crazy value, and it's sparkling hulk green.
I also set the roughness to 0 so now it's really shiny.
We can also change the normal map effect, I'll see what happens if the normal map is set to 0.
Yay, if we turn the normal map to 0, then we have a very shiny emerald rock.
Now we are going to check the surface material, we are going to edit the cube maybe.
Let's turn our cube into a slab and then we will apply a decorative brick wall texture, but first we are going to decide the quality of the asset we want to import.
In the detail view of the asset, at the bottom left of the options, next to the download button (green with arrow down), there is a dropdown menu with several possibilities.
low 1k
medium 2k
high 4k
highest 8k
Qualities possibilities that we need to assess what we want to use.
8k is really pushing it, we're going to go for 4k high.
Once the download is finished, we can click on the add button and it gets us to the content drawer exactly where our material was downloaded.
The path is All>Content\Megascans\Surfaces\Decorative_Brick_Wall_vi0lbih
there are 3 heavy files, the texture, and the material itself is very small.
Oh ! I wanted to drag and drop the texture but then unreal engine crashed, I sent the logs.
I launched unreal again, then applied the texture and this time it worked.
Now the brick material is pretty much the same as the former material, but now there is a special parameter which is called Global.
Global is going to control the tiling of the texture.
Inside the global, there are 4 parameters, the tiling and the offset, for x and y.
The tiling allows to stretch or squeeze the texture according to the axis, and the offset allows to roll the texture like a sliding ad.
You can also use the rotating angle to rotate the texture.
values change the angle in quarters of 1, so 0.25 will rotate the texture perpendicularly.
You can reset values with the counter clockwise arrow, and then the arrow at the top of the section appears, which allows you to reset every value at once.
Tip: You can jump to the location of the object material by clicking on the magnifying glass + folder in the detail of the object.
You can use ctrl + B to jump to the object location.
Now that we know how to handle the megascan texturing, let's go into the foliage.
