# Foliage Tool

There is a special foliage tool that you can get to by using shift + 3, but first we need to get actual foliage.
For that, we are going to get the foliag in the quixel bridge.
Let's search for a common fern.
Again we have a choice for quality, we choose High and now we see that we have different possible objects of ferns. Let's check them out.
We can check out the material with ctrl + B, but don't select the material with billboard inside of it.
We have 2 materials, 1 for elem 0 and one for elem 1, they share elem 0 but elem 1 (will billboard in it) is different, hence one fern with brown leaves.
If we modify things in this main material, it will affect all of our 3 ferns.
In Albedo I can select the color overlay for basic color change.
Above the color overlay, we can see the color variation. If you make it very big you will see huge differences between the fern colors, so just 0.05 would be enough.
We can change the roughness in the same way as usual, with shiny vs rough
Same with the normal map.
Here's something new, we can play with the transluency strength and its desaturation, it changes how much the light will go through the fern, and then how less colored the leaves below will be.
Then we have a new nice parameter which is the wind, it will add a new level of realism to the leaves, and we can control differenc parameters inside, such as the intensity,
the height, the speed, etc.

Now we're getting closer to nanite with the LOD. We notice that if we go away from the ferns, there is a bit of popping.
We can discover how the LOD is executed by going into the fern detail.
We can see an indication of the LOD in the fern edit, with 0 if you are really close and it goes up to 4 if you are far away.
There is a little option to change the LOD, so we can see what if the far away version looks like even though we are really close.
The billboard corresponds to the 4 version, which is why it's called billboard.
We see that the main material and the billboard material are very distinct when we try to change the main material color and zoom out, in the billboard version, the ferns still have their green color.
Now that we have messed with the foliage itself, we can go and check the foliage editor.

If we go into the foliage mode now, with shift + 3, then we go automatically to the paint mode, and then we can see at the bottom that our 3 ferns appear. This is because when we import foliage via the megascan, unreal is smart enough to realize that since it's foliage, we're probably going to use it in the foliage mode and then paint it.
This is called the foliage type. Of course, if some foliage you want to paint is not present in the foliage type list, then you can simply drag and drop it from the content drawer.
The paint sections contains details on the left with options about how you want to paint the specific object.
You have parameters such as the density, the radius, etc.
If you don't see the options, you need to click the button with a pen and click on it to make sure it is activated, when it is activated it is in blue.
If you look closely at the 3 foliages in the asset selection to paint, you will see that there is a little checkbox in the upper left corner of the image of the fern, and this is what you need to check if you want to select that foliage to paint.
I tried to paint and then undid it, but it works, it generate lots of ferns, this is a great way to progress quickly.
You can  select all 3 ferns at once and paint them together, it will use all 3. When you want to erase, just click shift and erase. You can erase a specific type of fern by only selecting it for the brush, regardless of whether you want to paint or erase, the brush will only act on what fern you have selected.
You can decrease and increase the brush size by looking at Brush Size in the Brush options of the paint. You can also hit the shortcuts, [ or ] for increase or decrease respectively.
You can increase and increase the density between 1 and 0 to paint more or less ferns at the same time. The base value is 0.5
You can go where the ferns are and press ctrl + A to select them all.
Remember that if you select more ferns than one and then edit the properties, it will change the properties for all of the ferns that are selected. If you want to change the properties for only one fern, then select one and edit and then select another and edit.
This works, the default value is 100 for 1 2 3, if I select 2 and set it to 900, then 3 and set it to 1000, they are done separately, and then if I select both and set it to 100 they both go back to 100.
Not that there is a separate density for the brush and for the ferns, if you set max density for brush and to top it off, set 500 for ferns, then you will have a lot of ferns.
They still look unrealistic though, so if we jump back into their material, we'll see their color variation and we can set it to 0.01.
Also, all ferns have exactly the same size and plants never have the same size.
We go into the painting settings to the Scaling and Scale X settings, leave the scaling to uniform but set thescaleX from 0.5 to 2.0
This way we have a nice range of fern size.

If you happen to paint over a mesh, like your wall on the floor for instance, you will notice that if you move the wall then the fern is stuck to the wall. In some situations you might not want that to happen, in which case it's good to go to the Painting and then look for the checkbox Static Meshes, and make sure that it is turned off. When on, it will allow the fern to stick to the wall, and not if it is turned off.
Not only will it not be attached to the wall, it won't even be on the wall, the ferns will avoid any static meshes alltogether.
