# Moving and creating objects

The snapping grid is automatically deactivated, but you can deactivate it in the grid section.

The snapping grid default is 10 centimeters, so if you want to move one block by snap every 1 meter, just do 100 next to the grid

You can have much smoother movement by deactivating the grid.

The same is true for rotating the object and scaling, up and down.

What's interesting for the scaling is that you are going to do the scaling according to the direction you're pointing (rgb cubes), but if you click on the white cube in the center, then you will not scale towards a direction but uniformally.

; for translate, q for rotate, j for scale.

' for local, . for global.

If clicking on the square between two axis for translation, you can do multi directional movement in that plane.

We learned a true new command ! Ctrl + d to duplicate. Should I remap this ? I don't think so because ctrl + D is already fairly fast and I probably won't need to do that a lot.

Also, for the translation, the last space on the right is the one for height, so if I want to set the heigt to the ground, just compare the last space to the ground.

When an object is duplicated, the name of the duplicate is the next integer. So for chair, it's chair2, chair3, and so on.

HOHOHOoooh ! As expected, there is a much more convenient way of duplicating, just drag an item in tranlation while holding Alt.

Lights are items to, and we can spawn a light in the level, just the same way as a sphere. That's another fancy way of getting more of the same object.

I bound the select mode to o, because it is the central key.

I need to make a note that I thought there was some weird binding with ctrl + space, but turns out that the mapping for these are different in each mode.
So for instance, ctrl + space will be content drawer for select, but switch between local and relative mode in translate.

Maybe I might remap ' and . a while later if there is a closer use.

I discovered a few kinds of lights. There is the directional light, infinitely far away, to mimic the sun, the point light, like a light bulb, a point emitting light in all directions, and spot light, a light that emmits a cone shape light.

Last way to get an object, we add it from the asset/content drawer. This is sweet, it reminds me of the oblivion construction set.

If you want to select multiple items, you can hold shift + click  to select several things, and you can remove an item from your selection by using
ctrl + click

Instead of dragging an item through a window and then another window angle like a quaterpillar, you can hod the shift button while dragging (in translate mode).

Following the tutorial, I selected 2 chairs and duplicated them, then dragged them in follow mode, and also rotated all of them together.

I played with the placing of items a bit. For rotation it's more efficient to use numbers to get the perfect angle.

you can use the End key (Fin on my french keyboard) to snap the object to the ground, well to the surface below it.

This is good because I wanted to place more lamps on the table but they were all below surface, but by placing them all above and then using end it works.

And of course it works for multiple selection too, hurray for trees.
