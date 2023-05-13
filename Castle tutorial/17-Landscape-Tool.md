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
You should ALWAYS have a way to extract resources from something close by
