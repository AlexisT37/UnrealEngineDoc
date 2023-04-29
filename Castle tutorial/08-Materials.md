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