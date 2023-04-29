# Materials

Let's make a new map, but first we save our assets.
New folder in Content folder, should be next to Starter Content.
Call it MyStuff.
To create a level, we can rightclick anywhere when inside the folder and select level, but instead
we're going to use a template level.
We're going to go to file and then New level and then basic.

This is nice, almost nothing, just the lighting settings and the ground.

The grid will be troublesome for the material so we will disable it using show and then uncheck grid.
we're also going to axis z-y and in the middle hover left click inwards to scale down the ground to a little ground.
Now it's quite tiny, don't forget to hit j to get in scale mode.
Another possibility is to use the numbers, 1 1 1 in every axis.
A nice little plate.

We're going to get a bunch of new assets, but these are not in the starter content.
Go to settings in the asset drawer, and check Engine > Content > EngineMeshes > SM_MatPreviewMesh_01
You can find it more easily by searching the name.

Then we create a post process volume, affect the entire world by details > Post process volume settings > Infinite extent (Unbound)
Then Lens > Exposure > Metering mode needs to be checked and set to manual. We set the value to 10.5
Make sure Lit > game settings is check on.
So there are lots of materials in All > Content > StarterContent > Materials.
To apply a material to a surface, just drag and drop it on top of the desired surface.

What's quite amazing is that the reflexion of the material onto another surface is visible.
Right click inside Content Drawer > create basic asset (section, not clickable) > Material (is green)
double click to enter it and edit material.
dock it to the top to switch easily between tabs by clicking Ctrl + Tab

We enter the Material Graph. I have seen graphs before, they seem to be governing the logic aspect.
The goal of every node you create is to be outputed in one of the outputs you see in the main node, like in Metallic for example.
Right mouse button to pan, scroll wheel to zoom in or out, right click hold to select several items.
There is a viewport for the material or whatever you are editing right now, it could be a bush, you can control the camera by using left click
and the zoom by using right click.
By default the preview is a sphere but I can go in the right corner of the viewport to select a different primitive.
Cylinder, Sphere, plane, Cube, or current content browser selection, which means I need to select a mesh in my content browser.
If I select a chair in the content drawer (Just one click on it), then i can use it our new viewport.
We get an error if we try to use selection without having clicked on an asset that has the proper type.
Then we go into the details pannel. This will match the graph node we clicked on.

On the right of the screen, there is a palette that contains all the different nodes we can add to our material or whatever we are editing.
We can also obtain the palette by right-clicking anywhere.

We search for Constants > Constant3Vector (we can search)
and we get a node that is used for color.
It uses RGB.
The default is black, but I can go to the details pannel to edit the color with a color picker.
I tried to look for the parameter but I forgot to select the vector3 node, you really need to select the node for the right details mode to appear.
Remember that there are two vertical bars, one is for the saturation and the other one is for the value. For any change to be visible at the end, you need
to make sure that the value is changed, even if you click on ok, because the saturaction is reset everytime you go out of the window.
We can connect one of the outputs of the node to the main node. We're going to connect the white to Base color. There are a lot of things you can do with the edges (Les traits) but so far I don't know the controls so I wait and use ctrl + z to cancel my actions in case of a mistake.

Now I go back to the main viewport and drag my material (in MyStuff) onto the unreal engine object, and it gets this nice shade of pale green.
There was a difference between my material and the material from the tutorial, in the tutorial the effects didn't apply directly. That's because you need to compile the changes by applying it. It so happens that I hit save and so that includes the applying apparently.
The apply button is on the top bar of the edit window, right between the browse folder icon and the Search button.
Apparently there is something going on with the switch tab button, ctrl + tab, and the save button. Indeed when an edit tab is saved, it is not included in the tab list anymore. That means the list only contains the currently "active" tabs, which means the tabs with unsaved actions in them.

Now we are going to edit the roughness channel instead of the color.

Roughness is a value between 0 and 1, for the smoothness of the material. 0 is really smooth and 1 really rough.
At first I thought it was the opposite but turns out the reflexion in the sphere made me realize my mistake.
We search for Constants > Constant1Vector (we can search).

To remove an edge, simply hold Alt and left click on it.
the smoothness is really nice because you can see the sky and the clouds reflected in the material.

Now we're going to make our material metallic.
It's the same, a gradient between 0 and 1, and the more you get close to 1, the more metallic it looks.
PBR is Physically Based Rendering, or PBR.
These values are clamped to 0 and 1 so if we select negative values or values above 1, it's just going to take it back to 0 or 1.
Usually for metallic, it's not going to be in between values, it's either going to be 0 or 1.

In the detail of the Unreal engine prop, there are 3 materials, element0, 1, 2, and presumably they all are connected to individual values.

Yes indeed, if we go to the asset drawer and drag our material to 1 or 2 it will replace the color of these sections of the prop by gold.
Let's take it back to plastic, and then we're going to want to make it so the texture of our prop is not uniform.
We go to All > Content > Starter Content > textures and we find T_Perlin_Noise_M.
we drag and drop it to our graph section of our material. In general, to add a texture, we can drag and drop it from the asset drawer, or we also can
right click anywhere, and search texture sample, and then select the texture of choice.
You can then connect it to the base color output.
We then delete the node for the constant value of roughness, and instead we apply the perlin noise to it. This will give a used effect to our material, because the random values of the perlin noise will make it apply differently on the surface of our prop.
With that, when applied, we get the interesting texture of the perlin noise upon our prop.
If we go into color mode with alt + 3, we see the simple color map of our objects without the effect of perlin noise or the lighting.

Now we're going to imitate dirt by getting the smudgier area somewhat browner.
We duplicate the initial color node, and then we're going to apply what's called a Linear Interpolate Node or Lerp (easier to search that)
This node will direct the application of the color to the black or white sections of the Perlin noise. That means that the clearer areas will look gold, while the darker area, smudgy, will look brown.
There are shortcuts for the various types of nodes.

1 + left click is scalar one, so just one value
2 + left click is scalar 2, x and y, so 2 values
3 + left click is scalar 3, so 3 values like rgb.

Now We have to properly connect the nodes so that we will have the perlin noise effect with dirt.
The gold is not connected to base color anymore.
The gold is connected to the Lerp A
The dirt is connected to the Lerp B
The Perlin Noise is connected to the Lerp Alpha.
The Perlin Noise is connected to the Roughness.

That means that the perlin noise is not only connected to the base color but also the roughness, and that the roughness and the color are distributed in parallel. What is white in the perlin noise is Smooth and gold, and what is black is Rough and brown.

Now, instead of lerping between a color and another color, we're going to lerp between color and another texture.
We're going to select the t_metal_rust.
If we open the texture inside the content drawer, we don't see anything, that's because the alpha channel covers opacity and it is on, so we need to go to the top bar in the texture view and click on the black on white A in a square and disable it by clicking on it. Then we can see the rust.
I notice that the edges can't be multiplically connected, which simplifies the possibilities.
Indeed, I only need to connect the rust to the lerp to have the connection to the brown texture dissapear.
Now our prop does look like it has dirt on it a little bit better than with the brown color.

Now we got a good basis for the materials.
