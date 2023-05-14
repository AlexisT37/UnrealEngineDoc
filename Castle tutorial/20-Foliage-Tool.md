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
The billboar corresponds to the 4 version, which is why it's called billboard.
We see that the main material and the billboard material are very distinc when we try to change the main material color and zoom out, in the billboard version, the ferns still have their green color.
Now that we have messed with the foliage itself, we can go and check the foliage editor.

If we go into the foliage mode now, with shift + 3, then we go automatically to the paint mode, and then we can see at the bottom that our 3 ferns appear. This is because when we import foliage via the megascan, unreal is smart enough to realize that since it's foliage, we're probably going to use it in the foliage mode and then paint it.
This is called the foliage type. Of course, if some foliage you want to paint is not present in the foliage type list, then you can simply drag and drop it from the content drawer.
