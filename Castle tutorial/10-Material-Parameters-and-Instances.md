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
