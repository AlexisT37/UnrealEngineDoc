# 15-Archviz-Lighting-Lumen

Let's start by changing map

All > Content > LightingExample > Maps > ArchVizRoom

At first we don't see anything because the room is without lights. But if we cleverly use the unlit view, we can clearly see that it's a simple modern room with windows, a door, a chair, and a table with a old-school phone, a cup of coffee, and a old-school alarm.

We start by adding a directional light, the sun.

Let's try to do a litte bit by ourselves, we'll add the sunlight and the sky.

I seem do have done good so far, but something else we can add is the effect to add the black void of the horizon. That's the height fog.

Add > Visual Effects > Exponential Height Fog

And in its settings, since we can see a little bit of it inside the room, we are going to set the Start Distance in Volumetric fog to the maximum of 5 000.
If we switch back and forth with Ctrl + Z and Ctrl + Y, then we can see the difference.

The value means, do not start fog unless we are 5 000 cm away from the camera.

The Sky light was added, if we check uncheck affect world in Light we see the difference.

Now we are going to set the sunlight and the skylight to movable, because we want to do so.

We also set the angle of light with ctrl + L so that just like in the video, the light does not reach the wall.

We don't forget to add a post processing volume with the lumen Final Gather Quality to 10 to reduce the noise.
For that, we also need to make sure that unbound is check and that way the post processing volume affects the whole level.

Now we are going to add soft shadows to the little objects, to make their lighting more realistic.

For that, we check the Lumen Scene detail and set it from 1 to 4. This will improve the shadows of the small objects.

At first I was scared because I could not see the difference properly, but this is just because of the lighting setting of the tutorial. If I add a light inside the room, the difference is unmistakable.

One last edit to the process volume is the manual exposure.

Under Exposure, check Metering Mode: manual
the level with go black, it's normal, and then set the exposure compensation (below) to 13.25.
Actually for me it's too bright, so I use 12.5

Now the setting for this level is done, and we can obvserve the changes in real time by using ctrl + L.

Now an important consideration is that this is very convenient because of the real time, but it might not be the best for every situation. For instance, if we have a scene with nothing but non-moving material, it might be better to bake in our lighting, and I suspect it might be a lot easier on the GPU.
Indeed, when baking the lighting, it's just overlayed as a texture and there is no calculation.
Also, for really good quality, bake-in lighting will still surpass lumen.
