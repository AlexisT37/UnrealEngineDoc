# Textures

We're going to start by downloading the free assets that are in the description of the video.
[Link](https://www.unrealsensei.com/asset/ue5beginner)
I made a save of it in C:\Users\hotar\Documents\Unreal-Engine-Content-Save
Unzip it and then we are going to import it into our unreal engine.
For that, we simply drag and drop what we need into the desired folder in the asset drawer.
We want:
SpanishPavement_basecolor.png
SpanishPavement_normal.png
SpanishPavement_Roughness.png

We'll find what a normal map is later.

We select the three and then we don't forget to save them.
SpanishPavement_basecolor looks brown but what is important is that when we look at the detail window then the sgrb check box is checked.
This is important for base color textures.
For the other two ones, however, we want srgb to be turned off so we are going to go ahead and do that because by default it is on, at least for the roughness. Don't forget to check that your changes are saved.

Usually, unrealengine knows how to set some of the settings according to the file, which is why srgb was already turned off. Also, in
Compression > Compression Settings, we have normalmap that needs to be selected (it's a dropdown menu).

However, if unreal engine doesn't figure it out by itself, then make sure yourself to set srgb to off and compression mode to normal map.

I tried to do the setting with graphs on my own:
The base goes into base
the normal map goes into normal
the roughness goes into roughness.

I know what the roughness and the base does, but I wonder what the normal map is supposed to do.

We can go faster in putting the assets in the graph by selecting them all and drag and dropping.

58:16, let's look ahead 10 minutes so that is 20 minutes.
That's amazing, taking notes wasn't a waste of time at all, same as going at regular speed. You actually need a lot of time and thought put into each section, so that you can commit the content to memory and be effectively able to download unreal engine into your brain.

I remember almost nothing from that extract I watched so far, so let's go back to regular speed, taking notes, and commiting to memory.

Well not exactly nothing, at least now I know that the normal map is going to be used to apply a fake depht, fake 3d dimension including fake shadow, to your 2d material.
Without the normal map, the tile texture looks like plastic, it has no depth. The normal map indeed adds fake depth.

If we go to add and add a point light (remove grid for seamless moving), then we can see that there are shadows. Let's try again without the normal map.
By comparing screenshots, the difference between with and without the normal map is quite obvious.
