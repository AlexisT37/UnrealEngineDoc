# Youtube starter course

So we go into the tutorial, be sure to start from nothing and select starter content.

We load the blank template, then go to file, open level and look for minimal default.

you can look around and move objects.

above the viewport, there is the toolbar with lots of possibility.

For instance, you can click on the cube with a plus sign to add something.

I selected a sphere, but you can also add other basic shapes. Once you have made the item appear, you can move it.

Right now we are in the selection mode, but we can switch between various mode to execute different actions.

For instance, you can go into the landscape mode to modify the landscape of the game.

There is also a foliage mode for everything tree and plant related.

On the right, there is the Outliner. The outliner is the list of all the objects in the world. One of the advantages of the outliner compared to the viewport is that you can select objects that are not in the field of view. For instance, I can select the chair even though I don't see it.

I mistakenly went to select the chair and then I went into the select and scale object, so I made the chair longer.

One other advantage of the Outliner is that with control you can easily select multiple items at once, no matter how far away they are in the wiewport.

Inside the outliner, you can create folders. Note that the folder does not seem to affect the interaction between the items in the game world so far, but we'll make sure about that later.

I made a chair folder and then moved both chairs inside it, it didn't seem to have any effect.

Inside the Outliner, you can click on the little eye on the left to hide and unhide objects, which is very useful when you want to get one object out of the way to get a clear view of some perspective without impacting the said object. Then, you can unhide it and move on.

Clicking on the eye icon will close the eye next to the object, which is a neat way to know whether an item is hidden or not.

Right below the Outliner, there is the detail panel where are all the properties of the project.

When you make a modification in the detail panel (after you click away from an edit in a value edition for instance), you can cancel it with ctrl + z

Clicking on an elememnt is in itself an action, but when you are inside the edition of a property, say scale, ctrl + Z will not do anything.

However, once you click away and do something else, the edition of the property is counted as an action. But nothing happens while you're editing a variable.

At the bottom, we have the Content Drawer. It shows the detail of all the assets you have, not only for this level, but on your whole unreal engine project I believe.

You can press ctrl + space to get to the content Drawer.

Be careful ! This is different from the content browser (note by future me, it's actually not different).

If you click on an asset in the content drawer (You can get to it faster by looking for it on the search bar of the drawer), if you double click on it then you will open a separate window with more detailed properties about the chair.

By hovering over the chair with your mouse, you can see many properties. I was curious about the "never Stream" property of the chair. Not much luck with google, but with chat gpt, even though it told me that there was no never stream property, which seems to be false, it told me that this was related to whether you are going to stream, or simplify the render of the object, depending on the proximity to the camera and the relevance to the current action in the scene. This might mean that for instance, if this is turned on, if I am very far away from the chair, then even though every tree and rock is low poly around it, the chair will have all of its detail rendered from very far away.

Later, we will go into the static mesh editor. I don't know what that is yet, but I'm sure it has to do with editing the skeleton of the chair. We'll see.

The content drawer works just like the file explorer on windows, which is really nice. We're going to look for a specific asset in the content drawer.

Inside the content drawer, we go into the All/Content/StarterContent/Maps folder, where we can see our little map with the chairs and table. It is called Minimal_Default. On its icon, we can see a little asterisk, which means that we are currently editing it. Once we right click on it and select save, then the little asterisk dissapears. I'm wondering if I overwrote an important file, but maybe we can download the map all over again.

Just as I thought, we can add the starter content from the content pack in the menu to add it to the project.

In the content browser, we click on add (little green plus), then we click on Add Feature or Content Pack, then we select Content (there are three options, Blueprint, C++ and Content), and then we can select the starter content.

You can dock out the Content drawer in the layout, and from now we have to assume that the content drawer and the content browser are the same thing, especially because they have the same purpose, juggle with assets in our project and organize them.

You can hide or show the tabs by right clicking on the top left corner of the tabs, it reduces the space taken a little bit.

The tabs are very useful because they are a good way to freely customize your ui. For instance, I can put my content browser at the top, at the bottom, or among the tabs in the right pannel which is supposed to be for the details of the object. There is a little difference between picking up a tab and the window it is in, so if it doesn't snap back to where you want it, make sure to hold it by the tab, not the window.

You can totally close the content browser as well, and if you go to Window, you can find it again, it is the second option. Note that you then have to click on one of the 4 possible content browser tabs, which means you can have several content browsers open at the same time, I tried it and sure, I had two content browsers open. This might prove useful if I want to switch between two different types of assets for some reason, and since in the search bar there is an option to create a custom filter, I'm pretty sure you can save a lot time that way.

By clicking on the little bars between the windows, you can stretch and squeeze them to your liking. This could be useful when you want to see more detail clearly in the Outliner for instance, or the details, but I suspect that when it come to the viewport, there might be a shortcut for fullscreen. We'll see about that later.

You can dock and then hide your windows into sides of the screen, it's nice because it can make more room for the viewport while having other windows large enough to see inside.

It can be a bit messy with the different tabs and windows, but they're always accessible in the Window menu anyway.

If I press F10, I can indeed dock all of my tabs/windows into the sides, which is pretty much like a fullscreen, I was right.

Alt + P is the shortcut to Play, and I can press Esc to exit the play mode.

Let's discover a windows that I don't know about yet, the World settings. Before continuing with the tutorial, let's explore it by ourselves first.

There seems to be a lot of entries in this new tab, things such as the gamemode override, the kill Z, the global distanceField View distance, or the Allow Tick before begin play.

The kill z value is the value for the kill zone, which, when reached, make it so that any actor or objects are killed or destroyed to prevent them falling forever and then creating memory leaks. -1048575.0 is the current value, and it's a minus, which means that if you fall below -1048575.0, you will get killed. the global distancefield view distance is the distance from the camera that the global distance field should cover. Here is some chatgpt:

"The Global Distance Field is a 3D texture that stores the approximate distance to the nearest surface for every point in the game world. It's primarily used for various shading effects, such as ambient occlusion and shadows, by providing information about the surrounding geometry. The Global Distance Field View Distance determines how far from the camera the Global Distance Field should cover.

Let's use a concrete example to explain this concept:

Imagine you're creating a game with a large outdoor environment, like a forest. In this forest, you have trees, rocks, and other objects casting shadows and interacting with the ambient lighting. To achieve realistic lighting and shadowing effects, you can use the Global Distance Field to approximate the distance between surfaces in the scene.

Now, suppose you set the Global Distance Field View Distance to 5000 units. This means that the engine will generate the Global Distance Field information within a 5000-unit radius around the camera. Objects and surfaces within this range will benefit from the shading effects provided by the Global Distance Field. However, objects beyond this distance will not have access to the Global Distance Field information, and their shading might not be as accurate or detailed.

Adjusting the Global Distance Field View Distance is a balancing act. If you set it too low, the shading effects might not cover a large enough area, resulting in noticeable visual discrepancies as objects move in and out of the distance field. If you set it too high, it can consume more memory and potentially impact performance. Therefore, it's essential to find a balance that provides the desired visual quality while maintaining good performance."

I copied the gpt segment with a concrete example in its own markdown file, it's really fantastic. I won't go into detail but in short if this is ticked some processes will be active before the player start playing, and a good example is a loading screen, if you want some event to be calculated and processed before the loading screen is over, for example night day cycle, then you can activate this.

Now that I think about it, there were too many occasions where a night day cycle was really bothersome. I think the best is to give total control for the player. The best, in my opinion, is to freeze the time at whatever you are rigth now, allow to set the time to your liking, and if you want, THEN, enable the day time cycle, but you should be able te accelerate or slow down the cycle, and disable it.

The settings for the gamemode are the override, that is to say the default gamemode when we start the current level, and then the gamemode selection. Note that you can import a gamemode from your assets.

By azura, by Azura, by Azura ! You can reload the default layout. All you have to do is to go to the window menu, then load layout, then Default Editor Layout.

Now it's time to the camera, but I think I will go to another markdown file for that.
