# Auto Landscape Material

First we need to migrate the assets downloaded from the tutorial into our project
It's at C:\Users\hotar\Downloads\0etq38Ro6eVZX7TK8pKQ_IntroUnreal5\IntroUnreal5\CastleAssets
We start by opening the CastleAssets.uproject and we can see the pieces of the castle, even with towers that have an empty interior ! (I checed with a light)
as well as mountains.

To migrate the assets, go into the uproject file, then in the content drawer
All > Content > CastleAssets
Right click on it and select migrate.
Make sure everything is selected in the new menu
then you have to select the destination
C:\Users\hotar\Documents\Unreal Projects\Immortal\Content
this is the destination
Upon importing the files, I have an error message for virtual shadow map and nanite assets.
This could be because nanite is a recent feature and the settings were not put in place when the video was released.
We can go to the project settings and set the Immortal level as the default level.
Edit > Project Settings > Maps and Modes > Default Maps > Editor Starter Map
select Immortal.
Now that we are back in our level, we want to start using the assets.
Select the following (left click on it)
All > Content > CastleAssets > Landscape > M_Landscape_Inst
and then go to the landscape and in the details find the Landscape section with Landscape material. Click on the left facing arrow in order to apply the M_Landscape_Inst
You can also drag and drop the instance into the square next to Landscape material in the details.
The landscape is completely black, but that is normal.
Go to Landscape Mode, and select Paint
In the paint we see a lot of dirt and rock material texture, this is nice
I want to apply the first, AutoMaterial, to our landscape.
Next to automaterial click on the + icon
you have two choices, select Weight-Blended Layer(normal)
and select the default folder structure that it offers
now our whole land is covered in grass.
What is very good about this material, is that when you sculpt, the material transitions naturally, it reminds me of age of empires, or zoo tycoon
When you sculpt and therefore increase the height of the material, the top area stays grass, but the sides become rocky.
Let's go inspect the edit mode of this material instance.
As we open it, we can see that it has a bunch of different settingcs.
For more convenience, we undock the details from the edit view, and we keep the view on the left, with the details undocked, it gives us a good view of the settings and the result on the main viewport.
Every layer in the details has a name with a letter and they all have the same kind of parameters.
A is a grass, B is the cliff, C is the mud, D is the dry soil, E is customizeable, so if for instance you wanted snow, you could go in bridge and get the snow there.

We are going to create Weight-Blended Layer(normal) for every layer until D included.

This is nice, I also learned how to do a ramp, you select two points and then you select Add Ramp, and then you have to flatten it or smooth it.
We can add a little bit of mud, because the mud will be used later for water.
Material D will be used for a trail.

I will leave the settings for the material as is, but it's good to note that you can adjust the common parameters, such as saturation, brightness, contrast,
change the color via tint, change the normal map strength via Normal Strength A, the roughness of the landscape (shining as a billiard ball or as rough as sandpaper)
You can change the specular strength, wihch I didn't know before. It's the power of the light reflection on any object, here the terrain.

The Distance Blend is a new property which seems to determine the way in which, in the distance, the grass transitions into a different texture.
It is a way to hide texture repetition, indeed, our grass is just a repeat of a square, and the distance blend is a way to smooth out the repetition effect so it looks better.

Then there is the mask, wich switches between a specific texture preassigned and you can otherwise choose another texture.
Here the roughness is used, and if you check off the mask it will not use the usual roughness texture.

There is the size and the  Size far, both control the tiling for the map, and with increase size the grass looks bigger and more zoomed in. One is for roughly up close, the other is for far away.

The StartOffset and the Blend Fallof control the way in which the blending start.

The B material has a group of specific settings, called the B_Material_Triplanar section of settings.
There are two settings, the UseTriPlanarProjection? Setting, which is a checkbox to use the triplanar or not
There is also the TriPlanar Sharpness, with a base value of 60.

The triplanar smoothes the textures and prevents us to get a stretched texture in case we have something like a cliff.
We use triplanar mapping on the B texture because it is the texture we are going to use on cliffs.
