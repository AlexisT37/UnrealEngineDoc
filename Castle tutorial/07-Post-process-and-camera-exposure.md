# Post Process and camera exposure

There can be a lot of pre-existing effect of lighting in any game made in unreal engine.

For instance, shadow feeling increase in dim lit room, and the brightness around feels brighter.

this mimics adjusting to light of the human eye.

We're going to duplicate our map, remember it is called Minimal_default

We can hit control + D inside the asset drawer to duplicate content, rename it to Post_process_example

post process example now has a bush
I removed everything except the bush and now the bush is on a cube next to the base plane.
Something I didn't thing about is that I could have also done a selection of multiple items in the outliner, it would have been easier.

I'm going to create a wall, and then a hut.

I created it and improved my efficiency a bit.
Now I have a small opening from the top to get some light.
Indeed the screen gets brighter, mimicking my eye adaptation to darkness.

You can disable this effect by going to the lit menu, going to the bottom of the dropdown, and then uncheck game settings.
Then the camera doesn't adapt to light.
Right below the game settings, there is the eve settings which might increase the overall bloom, you get brighter to the left, darker to the right.
The default value is 1.0. Note that you can't combine eve settings with game settings, in the sense that it will slowly move toward equilibrium and game settings.

In the Outliner, there is a specific object for the post-processing. We're going to visit it.
In the details, we have a lot of properties, including exposure.
In order to edit any properties, you need to make sure that they are turned on.
If you check the exposure compensation and have game settings activated, and move it to the left or right, then the equilibrium will become that new value,that is to say if you change the ev in the menu and then turn on game settings, it will gravitate to this value.

The post process volume is good to change things in the post processing after everything else has been rendered, because it affects only the camera.
For instance, we can increase the bloom. Be sure to hit ctrl + Z to unedit if you don't know the default value of something.

You can also hit the counter clockwise arrow that is a button that resets everything to its default value.

Let's now learn what is the vignette because it's a french word and I don't want to be confused by the french meaning.
The vignette effect is in Image effects.

The vignete is an effect that is as if you are looking throug a scope lens, black in a cicrle on the edges of the screen. The intensity make it more pronounced.
Note that default vignette is 0.4 but is disabled.

I can edit the saturation by going to the color grading option.
Then I go to Global and then saturation. It's in RGBY and if you switch it up it will edit the overal shade of the streen, like a green effect.
It seems it will tint according to the complementary color of the rotation.

You can go with the global saturation setting, 0 is black and white, 2 is very colorful.

lets DELET the post process volume to create our own.
Now we don't have a post process volume so we can create one from scratch.

Here is something interesting, the post process volume is actually a game object too and you have to put it in the level to activate it.

Let's check saturation and set saturation to 0, but we don't see the changes.
That's because by default the post process volume only affects what is inside of it.
That's AWSOME, if we go inside the cube then we can see the effect.
It stops at the frontier of the cube.

To apply the effect to the whole level, you need to go to Infinite Extent (Unbounded) and then check it.
This indeeds makes the whole level black and white.

This section is over, let's move over to materials.
