# Landscape tool

In order to make our landscape and our real castle project now, we will start by creating an entirely new map.

In your MyStuff folder, create a new folder called Maps.

In it, move the MaterialExampleLevel file.

We notice that Unreal Sensei asks us to move a second file in the folder, but I can't seem to find it in our folder. The name of that file is
MaterialExampleLevel_BuiltData

We're going to create a brand new level. When you create a new level (yellow in right click)  instead of doing it from the File menu, you notice that you don't have access to the templates. That's ok, because we want to start from scratch anyway.

The level is name LandscapeExample. Then we right click to jump inside.

Of course the level is dark like the other one, so I suppose we are going to start by creating the lighting.

Well I was wrong, we're starting by creating the landscape. We're going to go into landscape editing mode.

You can see the dropdown menu for the landscapes on the top left of the screen left of the add button (the cube with green check.).

You can switch between the various modes using shift plus a number, it goes from Shift + 1 to Shift + 8, as follows:
1 Selection mode
2 Landscape mode
3 Foliage
4 Mesh Paint
5 Modeling
6 Fracture
7 Brush Editing
8 Animation

In the landscape, there are several options in the main pannel on the left.

We can choose between 3 sub menus, Manage, Sculpt, Paint,

and then each of them have different options.

In the New landscape option, we can choose either Create New or Import From File.

It really looks similar to the detail view of other game objects, so I wonder if everything in the engine is either a setting or an object.
If that's the case, then the engine is really cleverly made.

In the unreal documentation, there are settings that you can execute into the create button, the address is the following:
<https://docs.unrealengine.com/4.27/en-US/BuildingWorlds/Landscape/TechnicalGuide/>

go to the Recommended Landscape sizes section.

We're going to keep the settings as default, and go at the bottom right of the menu and click create.
Good, now we seem to have our landscape but it's still dark, so let's go to the next step.
We are going to light the scene so we can work while seeing what is happening.

Let's start off by adding a directional light.

Add > Light > Directional Light

This is weird, when I added the directionnal light a checker ground was supposed to appear because of the light, but it seems I was actually upside-down in my camera, and when I looked up the checker was there. A good way to see whether you are currently upside-down or not seems to be using the colored model of the axes on the bottom left of the viewport, there is a red axis for X, a green axis for Y, and a blue axis for G, RGB -> XYZ.

If you are upside down, then the Z axis will point down, as it is supposed to point up normally, that was the case for me. When I looked down in order to to a 180 degrees like a looping with the camera, it set everything right.

You should never have to find anything, let's say: I want to plunder that ayleid ruin because I need welkynd stones because I need mana.
You should ALWAYS have a way to extract resources from something close by.

Then we are going to add a cube temporarily to help us figure out the shadows and lightings

No we don't want dark horizons, we want a sky. Let's go.
Add > Visual Effects > Sky Atmosphere.

As I lower my sun with ctrl + L, youcan see that the sun goes down and the skyl gets orange like a sunset.

Now we still have to problems, we have the up horizon but the down horizon is still dark, also our shadows are very pronounced.

We are getting light from the sun but we need lighting from the sky so it looks more natural.

Add > Lights > Sky light.

Note that there is the message that lighting needs to be rebuil in red! we'll rebuild later, let's see if it is mentionned in the video.

In the details of skylights, we need to check real time capture and make sure it is turned on.
Real Time Capture > false by default, needs to be true !

We also need to go into the Mobility setting and set it to moveable.
Both these settings are for the SkyLight, you can select the skylight in the Outliner on the top right if you are lost.

Now to solve the black void problem, we go to
Add > Visual Effects > Exponential Height Fog
We put it underneath the map because it's more practical, and we remember that we can change the distance by moving the widget: if we move it down we have less fog but if we move it up we have more fog. Don't be affraid to zoom in (use the mouse wheel to increase the camera speed), to see the effects.

We're going to leave it in the middle, a bit above the ground.

Note that when a widget with the arrows goes below a surface, then it becomes a bit grey.

Good news, the scene is pretty much good now, and apparenttly this is how you do for 90% of open world scenes.

If I control the ligth with ctrl + L, then we can see the lighting interacting with all the different objects.

Now let's get down to business, we're going to go into the landscape editing tool with shift + 2.
But before that we save all and we go to Build > Build All the levels.

With the mouse in landscape mode, we can sculpt and erase the terrain. The way it works is that sculpting lifts up the terrain like a mountain, and it creates a higher mountain the longer you hold the left click.

When you hold the left click in erase mode (eraser icon), it errase the height data and returns the height to basis.

note that it does that according to the ground here, so if I put a cube and turn it into a wall, it's going to sculpt the ground terrain and not the wall, also the terrain will clip into the wall.

If you hold shift and then left click you lower the terrain, it can go even below the ground.
We can create giant holes in the ground and it's not a hole that pierces the ground, it's a deformation of the ground !

In the landscape sculpt settings, you can change the settings.
Tool Settings > Tool Strength, and that will give more strength to the mountain or hole making.
As always, you can turn back the setting of your choice to default by clicking on the counter clockwise arrow.

The fallof is how the sculpture is going to look sharp or not, with no fallof, you create something that's almost a cylinder raised out of the ground, and with a lot of fallof, it is a lot smoother, like a mountain.

Dvorak is sweet for shortuts here, to increase the brush size, you can use the ] key on your keyboard, [ to decrease.

You can use the smooth option to make a sharp cylinder better.

The flatten tool with, regardless of the original height of the ground, flatten the current area. The height where it flattens to will depend on your first click, and the camera angle of course.
