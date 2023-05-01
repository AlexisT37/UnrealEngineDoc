# 16-Archviz-Lighting-Baked

Now that we've seen the power of lumen, it's time to compare it with the baked in lighting.

We start by duplicating the precedent level
First, we don't have the same intentions, so we are going to set the skylight to static, as well as the directional light.
The we are going to go into the post processing volume, and there are two parameters we want to change here.
It's the same for both, for global illumination and for reflexion, the method used to be lumen, and now we want to set it to none instead. But we still want to have a method selected, we don't deactivate it completely. Method is checked still, it's just that we select none.

We don't forget to recompile, because we see the message preview everywhere with black everywhere.

Now that it's done, the lighting is definitely not very good. So we are going to go into the World Settings tabs, it's a tab next to the details. If it is not there, remember you can select it by clicking on it in the Window menu.

Now we are going into Lightmass > Lightmass settings
Let's start by increasing the number of lighting bounces from 3 to 10.
Num Indirect Lighting Bounces
By the way Huge advantage !!! You can copy and paste the display name for easier note taking.

We're also going to increase Num Sky Lighting Bounces from 1 to 10.

Then we have the Static Lighting Level Scale. We are going to decrease the scale from 1 to 0.1. This will give us much more detail, at the cost of more building time.

To compensate for this, we are going to increase the Indirect Lighting Quality to from 1 to 10.

There is a general rule for this two values Static Lighting Level Scale x Indirect Lighting Quality should be equal to 1. This is why if we divide the former by 10, we should multiply the latter by 10.
In a same manner, if we had Static Lighting Level Scale = 0.5, then Indirect Lighting Quality should be = to 2 because 2 x 0.5 = 1

Now that we have appropriate settings, we can go ang click on Build > Build all levels.

There isn't much of a difference yet, and that's because the lighting quality is set to preview.

Build > Lighting quality > Medium

While we're at it, we're going to go to the postProcess volume and change the intensity of the bloom because right now it is too intense.
The bloom intensity will be set to 1 and the exposure compensation to 12.0

Now let's opitimize the rendering because the quality of the rendering depends on the quality of the textures. Since our textures are bad for now, then the lighting will be bad too. To increase the quality of the lighting through the textures, we go
Lit > Optimization Viewmodes > Lightmap Density
This will show you some kind of wierd blue and green appearance in the viewport.

The color grading is made to represent the quality, blue is to small, green start to be ok, we want ideally to get into the reddish range.

In order to increase the resolution of a static mesh, we select an object
Then we go into the details pannel, and over at Lighting, check the Overridden Light Map Resolution parameter.
Then we can change the resolution, here for instance the floor is at 64, let's increase it to a greater power of 2, let's say 256.
256 increases the quality clearly because the floor(unselected) becomes green, but we want to go even further so let's try 512.
It's still a green, but a bit yellower.

That's ok for now. Let's do the same for the walls because they are still blue.
Nice, the walls become yellow.
Lastly let's do the roof.
Floor is actually 1024.
We also did a couple of other elements, but no need to list everything, it's just an increase of Overridden Light Map Res in a power of 2.

Then we build all levels.

We note that here it takes a looooooong time to build, which is why lumen is so good because we don't have to calculate the lighting like that every time we make a change.

The shadows are so gooood now ! Unreal sensei thinks it's a bit to pronounced but for me it is really good.

Let's now change the ambient occlusion still because it's good to learn where it is.

We need to check it to override and then set the value to 0.

Ambiant Occlusion > intensity from 0.5 to 0.
Then to compensate we could change the exposure compensation again but frankly it's fine at 12 by me.

We need to change one last thing before having our ideal baked lighting.
