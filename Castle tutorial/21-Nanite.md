# Nanite

Nanite is a brand new way of looking at long distance geometry, and it enables us to do things that weren't possible before.
The polygon precision and number increase as you zoom in on the objects, and get bigger and rougher as you zoom out, and it allows for real time modeling of very far things.

Good thing is for me, it works for unreal engine 5.1 on static objects, and now we have it on 5.2 with foliage.
Another thing is that there is no landscape when it comes to the ground, everything is not a painting but an actual object, and if you click randomly on the ground, you will pull off a chuck of rock.

Let's get to the sea of Donuts !
we start off with a single donut made of 30 000 polygons, that is a very detailed donut.
For examle, ps2 era characters had about 3000 polygons for final fantasy X. That means that our litte donut has 10 times the amounts of polygons of a ff X characters, and now for fun we are going to duplicate it 100 000 times, wich is about a million final fantasy characters on the screen, and it renders no problem.
Now a computer can render it normally, it's just going to put the fps to 5 to 10 fps.
Let's turn on nanite. We select any donut and then we go to its location in the asset folder by pressing ctrl + B.
Then we right click and check the nanite box in the nanite setting.

Now we jump back to between 40 to 60 frames per second. WOAH !
We can see the nanites by clicking on Lit > Nanite Visualization > Triangles (make sure to have at least one asset using nanite, I used the mossy rock), and then you can see the nanites.

You can see which asset is using nanite or not by going to Lit > Nanite Visualization > Mask (also make sure to have a at least one asset with nanite)
Everything in green uses nanite, everything in red doesn't
Careful don't turn nanite on becaus we still have 5.1, of course it won't crash but still let's keep it disabled on foliage.
In the megascan, for certain assets, you have the nanite option in the quality for the asset, which is undoubtably the best quality.
It will take some time to download, as it is a very high resolution.
if we look at the wireframe view and compare a medium quality with a nanite quality, it's insane, we can totally make out the actual form of the rock from the nanite because it is so precise.

There is a lot of disk space necessary of course, but the upside is that the performance is actually ok, it's actually better than using lod, even if you have insane detail.
don't forget that it's alt + 3 for non lit, alt + 2 for wireframes, alt + 4 for normal
We want to compare all of the models in polygon quality, and for that it's better to hide our landscape
Hide = H, it's the shorcut for selecting an asset and then hiding it.
to show it, use shift + H or ctrl + h to show all actors, which means you make everything visible. If I hide the body mesh and the wall, and then press ctrl + H, it shows them both.
It's better overall to use ctrl because for shift + h to work you need to have the object selected, and when you hide it it loses the selection.
Now we look at all the different levels of quality, and we compare between lod and nanite. We can hit ctrl + E to go into the edit mode, where we transition between the lod details.
Notice that we can manually go and activate nanite for our asset, and that nanite automatically generates polygon. It is detached from the initial amount of polygons in the origal mesh, nanite will work, and you won't use the low poly count version of the far away lod.
If we look at our little mossy rock, we see that the number of polys decrease as we get further, from 3000 and something to 700 and then 300, but if we use nanite, we always stay at 3000 polygons no matter the distance, and we can see it when we use the wireframe view with alt + 2.
