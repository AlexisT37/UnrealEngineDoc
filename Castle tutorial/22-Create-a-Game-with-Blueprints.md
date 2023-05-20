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
