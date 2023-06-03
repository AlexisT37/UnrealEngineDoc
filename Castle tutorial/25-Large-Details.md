# Large Details

The most recommended steps when you create environments is to create large details first and then little details later.

For example, we are going to do the landscape and the mountains first.
Then you can move on to the medium details like the trees and the castle, and then finally the finer detail like the grass, pebbles and shrubs.
This is to avoid having to redo the smaller details if you decide to change a mountain for example.
We're going to start by sculpting and adding some random hills around the perimeters, a bit before the edges of the map.
Tool Strength 0.3
Brush fallof 0.5
Size BIG

The map is a big rectangle, but if it feels too small for us then we can increase the size by adding to the landscape tool
Manage > Add + and then you can add little squares by clicking, or even hold the click to do it in a painting way.

In the same way that we adde a Player Start so that when we start the game, we always start with the character and cameraat the same location, we want to do the same with the viewport it seems.

After having set the camera to a place that you like, go to the 3 lines button on the top left (same place where you show fps)
and click on bookmarks (there is a bookmark icon).

We do a couple of hillsides in the center and the back, that gives the impression that there is much more land than it really is. I don't like this kind of trick, but it is useful to know.

After customizing the landscape a bit with the Landscape section, we are going to add the background mountains.
We go into All > Content > CastleAssets > Meshes
we select the 3 mountain meshes
SM_Mountain_Eroded_01
SM_Mountain_Eroded_03
SM_Mountain_Eroded_04
(there is no 02 as far as I can tell)

Of course the mountains are extremely large, so they need to be reduced.
We are going to take SM_Mountain_Eroded_04 and make it 0.5 its size, that means setting the 3 axis values, x y z, to 0.5
You can do this 3 times or you can click on the lock icon and that will set all the 3 if you only set 1.

We're also going to se the exponential fog a bit lower in order to enjoy the far away landscape.
We're going to lower it down a bit and we're going to set the fog height falloff to 0.3 instead of 0.2

Unreal Sensei added another manny to see the height of the hill that would welcome the castle, and realized that it was supposed to be a lot bigger.
I'm just going to move the one we already have.
