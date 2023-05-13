# Landscape Material

Now just like with objects, our landscape need some material to have its good textures. We're going to create a new material for it.

We're going to create a new material in All > Content > MyStuff
and all it M_Landscape. Then we are going to go inside and right click to add a new node, and what we want is
LandscapeLayerBlend

It doesn't have any inputs, (cicrles with tiny arrow going right on the left portion of the node), unlike the main node which has 19, like base color, roughness, etc.
We need to specify the inputs in the details of our new node.
The inputs are going to be layers, like for instance a grass layer, a sand layer, a dirt layer, etc.
When we go in our main viewport, we'll be able to paint these layers on our landscape.
In the grahp, select our new landscapeLayerBlend and then go on the left to the details, you should see Material Expression Landscape Layer Blend, and inside you should see Layers, and in Layers there a little plus button + with a cicrle around it.
You can use that to add layers.
Once you have added the layer, don't forget to go to the left and you see a triangle pointing right that is for unfolding all the parameters of the layer.
For a start, we're going to create two layers, one for grass and one for dirt.
When we create a layer, we can see an input in our LandscapeLayerBlend node, it is first called Layer None but then it becomes what we named the layer like Layer Grass.
You have a Trash bin icon that deletes ALL the layers, and inside a single layer you have the index (starts at 0 ^^) and on this index there is a dropdown menu for the actions you can do on the layer. The delete option will delete the specific layer.
You can also insert, delete, and duplicate. Insert will insert another new layer, and duplicate will duplicate the current layer.

Now that we have our layers, it's time to apply some textures onto them. For that, we go to the following
All > Content > StarterContent > Textures
We're going to drag and drop T_Ground_Grass_D into the graph because we are going to use it for the grass.
For the tutorial, the rust texture is used for the dirt, it's called T_Metal_Rust_D

We hook up the textures to their respective rgb inputs (RGB is the top one, and it's in white)
Then we hook the output of the LandscapeLayerBlend into the base color input of the main node, which bears the name of the material, M_Landscape
