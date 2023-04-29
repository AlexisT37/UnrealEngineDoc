# Material Parameters and Instances

It takes a while to save and compile our material, so we are going to create some parameter. That way we can see the changes in real time.
It reminds me of yarn watch for js.

We are going to start by creating a material instance that will hold all of our parameters.

from the viewpoint you can directly access the material used by going into the details and then clicking on the icon of the folder with a magnifying glass on it. This brings us to el famoso spanish pavement.

We right click on it and then select "Create Material Instance".

We call it MI_SpanishPavement
MI because it is a material instance.

The big difference is that when compared to the other edit view of the material, we don't have the graph.

We can choose to make one of the variables in the graph of the original material exposed to the instance.

We can go to any node, right click on it, and select convert to parameter. Then if we go to the left of the screen, there is a detail tab but there is also a Parameters tab.
We call our first parameter size. To rename it outside of the creation prompt, we go to the detail tab and edit the Parameter Name inside of the General category.

If we save and go back to our instance, we can see the new parameter, it is called size, and if we slide the value it will get big and then small, both on the left and the right.

if we assign the instance to the floor by drag and drop it and then go int the editor of the instance and slide the variable, we can see in the main viewport that the texture is changing in real time.

We can also convert the new color 3vector into a parameter, call it color tint, and again, with the editor in view, we can adjust the tint and see the changes in real time in the main viewport.

Let's add another parameter with the normal map.

We go into the original material and we add a new type of node: the normal node. This node will be connected to the normal map.

The node name is FlattenNormal. This will make it able to increase or decrease the effect of the normal map.

This new parameter is awesome, we can increase the depth of the shadows. Just like the size, it is symetrical from the 0, down and then up into the infinity.

Now we're going to add a multiply node for greater effect on the roughness. Then a 1 + click that I will convert to a new parameter. But
I can go even faster by holding the S key and click to directly create a new constant parameter.

It will ask us for a name, and then we connect the output of the parameter to the B of the multiply.

We are going to change the default value, because here the default is 0 and it is very glassy we don't want that.

Then we reset the material values to 0 by clicking on the counter clockwise icon.
