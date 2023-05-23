# Castle Intro

For our castle we use the third person template, no ray tracing and we don't use the starter content.
We create a new folder named Maps in the Content folder.
We create a new level and we call it Immortal.

We create it and get a completely blank unreal level.
We go into landscape mode and get in new in the left of the screen, we keep everything as default (keep in mind that there is a difference between our projec and the video tutorial here, our New landscape detail has the option Enable Edit Layers enabled).
We still can't see the landscape, because we need to add a directional light.
Add > Lights > Directional Light
When the light gets in, it is still dark, which means that we are still under the floor. I want to drag my light higher, but I forget that I am still in landscape mode so I sculpted a big Mound, and I hit ctrl + Z to remove it. Now I can finally see above ground, and there is a light.
We add a sky
Add > Visual Effects > Sky Atmosphere
Add a cube and put it on the floor
Add a mannequin for huma size scale
All > Content > Characters > Mannequins > Meshes > SKM_Manny
We look at the shadows on the cube and we see that we need a little bit of blue tint (I don't see it, I am not attuned to it yet)
We need to add a special sky light that will be reflected blue on the cube.
Add > Lights > Sky Light
Actually, as it spawned, I was able to see the difference with the new blue light.
Set the skylight to have realtime capture turned on, go to details > Light and there is a Real Time capture below mobility and above Source Type.
add the exponential height fog.
Add > Visual Effects > Exponential Height Fog
Also, add a post process volume
Details > Exposure > Metering mode = Manual
Details > Post Process Volume Settings > Infinite Extent (Unbound) = 1
Details > Exposure > Exposure compensation = 10.5
I did something special here, I didn't like the following message as I built my lighting

"No importance volume found and the scene is so large that the automatically synthesized volume will not yield good results.  Please add a tightly bounding lightmass importance volume to optimize your scene's quality and lighting build times."

I couldn't see the effect of the post processing volume exposure compensation and I believd it was because I needed to build the lighting, so I build and saw the message.
To remove the error message, I added what is called a LightmassImportanceVolume. I believe it is done to limit the lighting work outside of the boundaries, for instance there is no point in lighting the map 5 km away from you, so you save on ressources.

In the end the light effect was not there for another reason, I simply hadn't checked the Infinite extent unbound button.
Lastly, add the volumetric clouds in visual effects to have a less empty sky.
