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
