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

1. **Polygons**: The "simple" model could have a lower polygon count, making it less detailed but also less resource-intensive to render. This can be useful in scenarios where performance is more critical than visual fidelity.

2. **Textures**: The "simple" model might use simpler or fewer textures. For example, it could use a lower-resolution texture, or it could avoid certain effects that require additional texture maps, like normal mapping or specular mapping.

3. **Rigging and Animation**: The "simple" model could have a simpler rig (the system of bones used for animation). For instance, it might have fewer bones, making it less flexible but also faster to animate.

4. **Level of Detail (LOD)**: In some cases, the "simple" version might be used as a lower LOD. Games often use lower-detail versions of models when they're viewed from a distance, then swap in the higher-detail version as the camera gets closer.

Remember to check the specific differences in your case, as the meaning of "_Simple" can vary between different assets or creators. It's always best to look at the specific characteristics of the meshes in question within the Unreal Engine editor or another 3D modeling software.

Since in the tutorial, UnrealSensei selects manny, not the simple version, we'll do the same.
