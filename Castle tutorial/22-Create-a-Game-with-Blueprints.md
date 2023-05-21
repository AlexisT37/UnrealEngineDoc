# Create a Game with Blueprints

Now we can start making our final level.
We are going to use our original level, and for that we are going to duplicate the level.
It looks like we are going to start by setting the controls for our game.
Let's go into the world settings, if you don't have it remember to go into Window and then check World settings.
In the world settings, we should go to Game Mode > Gamemode Override > BP_ThirdPersonGamemode.
You wouldn't have it if you didn't install the third person asset. However, you might want to add a custom gamemode, or you properly imported the asset, so you can manually assign the gamemode by doing the same thing as the material, go to where the gamemode asset is and then click on the left-looking arrow in a circle to assign the gamemode to the currently selected gamemode in the content drawer.

We can hit alt + P to get inside the game, and our chararcter will drop in where the camera is .
Interesitng point, I can step on the wall on the floor, but for some reason I go through the grassy rock.
Also, my character model has the same model than the one in the corner, but it is completely independent, that is because the dummy in the corrner is just a static mesh without any control logic attached to it.
If you want to access the mouse while being in game mode, you can press shift + F1 to regain the mouse control.
The gamemode is in

C:\Users\hotar\Documents\Unreal Projects\tutocastle\Content\ThirdPerson\Blueprints\BP_ThirdPersonGameMode.uasset

the person character is in the same location, in the content drawer it is in
All > Content > ThirdPerson > Blueprints
and the name is BP_ThirdPersonCharacter
Remember that these are the same locations, just different models of navigation.

We finally get to the blueprint where we can edit our character.
YEEEEEES THERE ARE THE CONTROOOLS !
There are different tabs in the edit mode of a character, and currently we are in the event graph.
we can select the event graph, the viewport and the construction script.
In the viewport, we see that the character model is made of component just like the level.
We can see what's looking like a camera behind our character, as well as its model.

You can replicate the controls of the main viewport in the blueprint viewport, you can focus, with u (F key on french keyboard)
you can hold alt + left mouse button to rotate around the focus and alt + right to zoom in or out.
On the top left, we have the equivalent of our outliner on the right, which contains all of the components of the blueprint.
if you select a component in the component sections, you still have to go back to the viewport in order to focus on it.
Once you have selected a component, you can change its properties in the details pannel.

Just like the material, we are using the female model right now and we can switch to the male model.
To do that, we have to be careful with what we want to select in the component, we don't want to select the whole bp third person character, we want to go inside in the hierarchy and select the Mesh. This is where the mesh menu in the details will appear and where you can change the skeletal mesh asset.
instead of SKM_Quinn_simple, select SKM_Manny_simple.

## Question for chatgpt

I can change the mesh I select for my character, I have manny an quinn, which are respectively the male and female model. However I have two possibilities inside these choices, two different mesh files:

SKM_Manny
SKM_Manny_Simple
SKM_Quinn
SKM_Quinn_Simple

What is the difference between the regular mesh and the _Simple mesh ?

The "_Simple" suffix on the mesh files typically indicates a version of the model that has been reduced in complexity compared to the original. This may involve lowering the polygon count, simplifying the texture mapping, reducing the skeleton's complexity, or other measures to decrease the rendering cost.

Here are some possible differences:

1. ***Polygons***: The "simple" model could have a lower polygon count, making it less detailed but also less resource-intensive to render. This can be useful in scenarios where performance is more critical than visual fidelity.

2. ***Textures***: The "simple" model might use simpler or fewer textures. For example, it could use a lower-resolution texture, or it could avoid certain effects that require additional texture maps, like normal mapping or specular mapping.

3. ***Rigging and Animation***: The "simple" model could have a simpler rig (the system of bones used for animation). For instance, it might have fewer bones, making it less flexible but also faster to animate.

4. ***Level of Detail (LOD)***: In some cases, the "simple" version might be used as a lower LOD. Games often use lower-detail versions of models when they're viewed from a distance, then swap in the higher-detail version as the camera gets closer.

Remember to check the specific differences in your case, as the meaning of "_Simple" can vary between different assets or creators. It's always best to look at the specific characteristics of the meshes in question within the Unreal Engine editor or another 3D modeling software.

Since in the tutorial, UnrealSensei selects manny, not the simple version, we'll do the same.

## Event Graph

The event graph contains all the nodes for our third person character.

Sometimes the event graph will be closed, if that is the case you can come into event graph on the left in the My Blueprint menu, in Graphs double click on Even graph, its icon is a little graph, 3 squares with edges.
You can change the windows just like in our main level editor.
In the same way, we have our panic button in case we mess up the display, we go to Windows > Load Layout, default Editor Layout.
BLESSING, since I am always affraid of messing up the interface, I can always go back with this.
If there is a subwindow or a tab that you don't think is useful, you can always use the scrollwheel button click to remove the window.
A good example here is the Compiler Result, but oddly enough it is not present here for my unreal enginge, probably because of some update. We could find it using the window menu, and then in the Graph Editor it is there, we jus need to check it. If we click on it with the scroll wheel it dissapears.

Let's go to the jump button part of our graph.
We have a subsection in the graph that is named Jum input - jump can be configured in the CharacterMovementComponent
In this subsection, we have 3 nodes, with one red node on the left, named EnhancedInputAction IA_jump
on the right we have two blue nodes, one named Jump, and one below named Stop Jumping.
The red node has 7 outputs and 0 input, the 2 blue nodes have 2 inputs and 1 output.
The red node has
triggered
started
ongoing
canceled
completed
action value
input action

the blue nodes have inputs
arrow symbol white
target (self)

output: blace arrow symbol.
it seems the black vs white arrow symbol is to signify whether the output/input is connected to something or not
the red node is connected via the triggered output to the arrow input of the upper right node jump
the completed output of the red node is connected to the Stop Jumping node via the arrow input

We notice that there is a difference between our subsection and the subsection in the tutorial.
In the tutorial there is another set of 3 nodes, which are not present in our version.
However, we are able to jump anyway, so maybe these three nodes where added by unreal sensei or maybe they were streamlined to be merged into the already existing nodes.
We're going to find out what these do by moving forward in the tutorial.

Let's test again: we can indeed jump, so it must be working properly.

we're going to add a player start in our level, this is where the player spawns when we click play.
Add > Basics > Player Start

We put the player start on top of the brick wall, looking toward the mossy rock.

Now we are going to do some fancy debugging, we are going to have the player act in the viewport and see the blueprint flow at the same time.
We start the viewport and make sure the graph and the viewport can be seen at the same time, then we select the debug mode on the top right of the screen.
Then in the graph toolbar at the top, we go to folder selector bar, should be at no debug selected, and we select the one we are currently in which is
BP_thirdPersonCharacter0(spawned), the spawned should be the one we are using right now logically.

It's interesting to note that while we are playing, the whole graph is circled in yellow.
when we jump in the viewport, we see some flow activated on the edges bettween the graph, first between the red and the jump, and very quickly after between the red and the jump stop.
it goes Thick bright orange/red, then thinner yellow, then back to gray.
Whatever node in our graph that is being activated will have red/orange versions of the edges, so if we move or turn the camera, the corresponding edges light up.

Now that we see how the graph basically work, we are going to add a functionnality. We are going to make it so that when we press F, the character ragdolss just like in gta 5.
We want to right click to add a node, and we are going to type keyboard F and that will find the event listener for the F key being press.
This node is under the sub category keyboard events.

We are going to check if the node F works by creating a resulting node, print screen, so that when we press F it is going to print something on the screen I suppose.
To connect the nodes, we drag and drop from the input arrow to the output arrow.
remember, alt + click to remove the edge.

the initial string was Hello but we are changing it to Event was fired!
There a development only section in this node, and we can decide whether we want to print to screen, to print into the log, the text color, the duration of the display, and the key but I don't know what the key does. After looking at the tooltip, if we add C, then pressing the C key will have the same effect. I can see that this could be useful to quickly add 2 possible inputs to a key, like we see in many action games.
We set the text color to orange with unrealSensei, but I manually edit the RGB to set it to basic RED.
Now we jump back into the viewport and we can see that the message the event was fired! appears in red on the top left of the screen.
It will do it as many times as we press the key even if we go very fast.
Now US deleted the node but I'm going to leave it, we'll see if we can connect one input to many outputs.
I could get my node and then connect the edges, but instead I'm going to drag and drop to nothing, and it will get the menu automatically for a new node, and then we can select our node.

Aha, interesting, we can' connect our nodes the way we want, with a one to many relationship, maybe because of the sequencial nature of C++ like many other languages ? But instead we can definitely have a sequence where we have our other event and then we have our message.

Now here is how it happens: we have our initial node connected to the print, and we get our mouse from the output of the F and drag it into nothing, and instead of making a new node directly, it's going to insert the node BETWEEN the F node and the print node.

We have a Mesh node, representing the mesh of our character, and we also have the actual event node which sets the collision to enable.
We went to check in the viewport, the message was there but no collision change, perhaps we need to add more layers.
Now the mesh component is connected by default, but if we wanted we could have fetched it from te component window, by drag and dropping it into the graph.
it's the mesh(characterMesh0).
We need to se the collision to collisionenabled query and physics for the collison to change
I was thinking maybe the no collision enables noclip, but it's still not that. For now no collision really seems to do nothing.

So what we had to do was to add the nodes that handle the ragdoll, and I was also able to add the print node at the end, no problem

For every node, there was (mesh) at the end because it references the mesh, and it goes in this sequence
SetCollisionEnabled
set query and output

SetSimulatePhysics
Simulate physics in the Set simulate physics node should be checked to turn it on.

SetPhysicsBlendWeight
In the physics blend weight (mesh), you should set the Physics blend weight to instead of its default value of 0.

then the message print.

Now here is something interesting, we can have all 3 nodes connect to the same mesh, instead of 3 different references. Here is an example of where you actually CAN have edges that come from the same input.

You can double click inside an edge to set a rewire node, it doesn't do anything it's just for the sake of presentation.
We make a cut between the simulate and the set physics blend weigth.

In the debug mode, we can see that the edges go into activated mode.
For the obstacle course we want to create, we are going to use a blueprint. For that we need to go in our content drawer, and then create a blueprint next to the third person character blueprint.
For the type of blueprint we select Actor.
We are going to add a Cylinder inside of it, the add button is on the top left inside the blueprint detail
Now that we have a cylinder, we can place it inside of our world. But we also have to edit it to add a collision capsule.
Add the Capsule Collision then drag and drop it inside the cylinder in the conponent section, NOT IN THE VIEWPORT of course. If everything goes well, the capsule collision should be a child of the cylinder.
Then we go back to the graph and we go to the list of event on the right, we need to scroll down
then we start from the output and we target to the third person character (the character, not the gamemode).
We should start the drag and drop from the Other actor.
Then we set a print string, tested and it works, it appears every time my character hits the cylinder.
Now we want the character to ragdoll and die whenever they hit the cylinder, so we need to go back to the graph of the character and add a custom event.
We right click somewhere above the F key node, and we select add a custom event...
We call this event death.
Then we connect the death event to the start of the sequence of the ragdoll, the set collision enabled node.
then you go to the cast to BP_ThirdPersonCharacter, and where the main output goes to the print string, the Add BP third person character, and this will point to death, just select it in the search, there is only one function.
Now it's very easy to avoid the pillar, so we are going to add some difficulty to it as an obstacle course.

For that we go back to the graph for the cylinder, and we look at the other nodes, specifically the event tick.
The event tick could be absent from the graph, so in that case we can get another one by right clicking searching for event tick
In our cylinder graph it is present but disabled, like 2 other nodes. We have eventbeginplay, eventactionbeginoverlap, and eventtick
the event tick runs every fram, and we are going to attach it to a string print called activated.
With that we can see the message being printed all the time, because all the cylinders are printing it every frame.

We're going to add another event, call add actor local rotation.
we have rotation parameters, we are going to select 5 for x
Aaaaah absolutely beautiful, the cylinders rotate just like i rotate my lightsaber, and they get me when I pass, hilarious as well because even though the camera doesnt' move, they do catapult my ragdolling body to mars. I love this !

Now the problem is that the rotation is frame dependent, and because of that if we change the fps, we get a much lower rotation. We should get something time dependent maybe. The command that was used to make the fps test is the same I used at the beginning before setting the frame constantly in the settings.
t.MaxFps 30

We're going back to the graph to add what is called a rotator, for that we drag the edge and search make rotator.
Then we drag from the event tick and select multiply.
Now the output of the multiply is going to be connected to the X input of the make rotator node, and we are going to set the multiply value to 5.
It is insanely slow, so we are going to set the multiplier to 100 instead.

So now, I'm not sure but it could seem that we get 100 rotations of 5 degrees per second.
I did a bit of adjustment for the direction of the rotations, it's not easy to see where the rotation is looking but I did it. In the future I should try to find a way to accurately know where the rotation is facing based on the arrows. Speaking of arrows, for the player it's not easy to see where the cylinder rotation is facing, so we are going to add arrows just like the selection translation arrows but visible by the player during the simulation.
For some reason I could not get the structure of the cylinder and I thought I hadn't followed the instruction because I could not see the components anymore, but I went to window and loaded the default window and there it was again, phiew.
In the hierarchy, the arrow should be above the cylinder. We make it blue by setting the color numbers.
I can see the blue arrow on the stopped version, but I can't see it when I play the simulation.
Ooooh I misunderstood the point of the arrows, they're NOT visible to the player in the simulation, it's just for me. Well I was talking about a way to guess the direction of the rotation, this is actually very convenient, thanks UnrealSensei

This is perfect, all I had to do was to adjust the arrow direction to match the cylinder direction in the edit view, it seems that the proper arrow is the green one when we are in local mode, and then we are good.

Now we see that the rotation of the cylinder is the same everywhere, we want to have different speeds and we want to edit the speed independently for every cylinder. You gessed it, we are going to do a parameter for the speed.
This parameter, variable for the blueprint, can be added by clicking on add on the left under the variables section. We call it rotation speed, and set the type to float. Then we can drag and drop it into our graph, and we have to choose between setting the variable and getting the variable. At first we are going to get the variable.
Then we connect the output of the variable to the lower input of the multiplier, where it used to be 100.
Now this variable was born of the previous hardcoded setting, so if we set it to 0 then we have no rotation at all, and if we set it to 100 we have the same rotation as before. After building and saving we can go to the viewport of the level and edit the variables independently for every cylinder.
But waiit I got ahead of the video, actually I don't see the variable when I click on a cylinder, something must be missing.
Aha ! Yes, we need to go to the variable in the graph, and check two settings
Instance Editable check
and
Expose on Spawn check
and now we can edit the variable on every different instance.

Now we are going to set an end goal for the course.
Let's add a statue to symbolise the end of the level.
I'm going to add the sm statue, and even though us did'nt, I added a poit light because my end plateau is dark.
We are going to set the satue to gold material.
I added a second light by duplicating the 1st one with alt.
We're going to add a trigger volume to the statue
Add > Volumes > TriggerVolume.
We want the volume to collide with the statue and being around the statue, so when we get near the statue it triggers the volume.
Now we need to add some logic to the volume, and for that we are going to edit the level blueprint.
Every level has its own blueprint.
Right next to the add button for the level (cube with green +), there is a graph icon and that is the blueprint icon. Select Open Level Blueprint
The blueprint has the name of the level, here it's gamemap.
Now we need to remove the existing events, they are deactivated but we don't want them.
Also we need to make sure that the trigger volume is selected before we open the blueprint.
What is good with the selection of the volume is that when we right click inside the graph, we get a bunch of options that are directly related to the volume, which saves a lot of time.
We go into
Add Event for Trigger Volume 0 > Collision > Add on actor begin overlap
In the same vein as our death ragdoll event, we want to make sure that the overlap is triggered relative to our third person character specifically, not anything else.
drag output to graph and then search for third person, you will get
cast to bp_thirdpersoncharacter.
Be sure to select the character and not the gamemode.
Again, to make sure that the event is working, we want to associate a print string with the event.
It's not working so far, I must have forgotten something, let's check the video.
Hoho, it seems that it should work, so there must be something wrong I did, let's try to troubleshoot.
It could be that  I did the wrong input output for the node onActorBeginOverlap,
in my case it is between overlappedActor and Object, and it should be between OtherActor and object.
let's fix it and then test again.
It works ! Let's goooo

Now let's make a win screen. For that we need to create a user interface.
We go to our All > Content > ThirdPerson > Blueprint folder
and create a new User Interface (in the right click menu, at the bottom of the menu, it's sorted alphabetically)
We select widget blueprint
We then get a window for the choice of type of widget, and we can select any class but we have a common choice which is user widget.
We save and go inside of our widget, on the left there is the palette tab and the library tab, in the palette tab we select add, and we search for canvas, it gives the canvas panel. We drag and drop it into the middle screen, and it gives us a green rectangle. This will be the frame for our message.
Then we search for text and drag the text into the screen.
In the detail of that text, there is a parameter to change the text, we type you won the game!
We increase the font by selecting the size parameter in Appearance > font
Then when we select the frame outside, not the text area, there is a flower at the top left, the flower is there to help us center the image. If we put the flower in the middle of the text, it will ensure that the text is in the middle of the screen, no matter the screen resolution.
The flower anchors the text in the middle of the screen
then we go back to our blueprint for the widget, we remove the print screen node, and instead we are going to connect the action to our win screen.
I don't delete the print screen in the gameMap blueprint (open level blueprint on the top next to the add option)
and I attach the output of cast to third person chararter to "Create Widget"
In this create wid8get node, we can choose the class so we select the winscreen widget
Since by default the winscreen is hidden, we can't just attach it we have to show it as well.
For that, we add another node to the output of the create widget, and we search for "viewport" which gives us add to viewport.
Now remember to not repeat the mistake from earlier, check carefully where is the output and where is the input, I was off again, you have to start from the output return value of the Create Win Screen Widget node, but I started from the regular arrow output.
Now the final step was te make sure the character could not avoid the obstacles by flattening the platform around the obstacles, making the plateform thinner, but my obstacle course made it already impossible to avoid the obstacles so I was good. That's it for our first obstacle course video game in unreal engine.
