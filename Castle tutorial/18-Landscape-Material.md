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
You have a Trash bin icon that deletes ALL the layers, and inside a single layer you have the index (starts at 0 ^^) and on this index there
is a dropdown menu for the actions you can do on the layer. The delete option will delete the specific layer.
You can also insert, delete, and duplicate. Insert will insert another new layer, and duplicate will duplicate the current layer.

Now that we have our layers, it's time to apply some textures onto them. For that, we go to the following
All > Content > StarterContent > Textures
We're going to drag and drop T_Ground_Grass_D into the graph because we are going to use it for the grass.
For the tutorial, the rust texture is used for the dirt, it's called T_Metal_Rust_D

We hook up the textures to their respective rgb inputs (RGB is the top one, and it's in white)
Then we hook the output of the LandscapeLayerBlend into the base color input of the main node, which bears the name of the material, M_Landscape

We save everything.

In the Viewport, we go to the details, because we can't just drag and drop the material onto the landscape.
Instead we select our material in the landscape material section.
Landscape > Landscape material, then we go to the content drawer and we left click to select our material, and then we click on the little
arrow that points left. That will apply our material to the landscape, now it's all shiny black, weird.
That's because Unreal Engine is not picking up any layers, so it defaults to black. We're going to have to manually apply those layers.

Now we are going to do in landscape mode, and there is a set of 3 tabs right above the various landscape tools, Manage, Sculpt, and Paint,
we go to paint and now we can select our layers.

Now we have an error message that says that This layer has no info assigned yet. You must create or assign a layer info before you can paint this layer.
Right next to the layers, click on the add button (it's a plus +) and select Weight-blended layer (normal). It's going to create the new
arborescence for us
All > Content > MyStuff > Maps > LandscapeExample_sharedassets
The default name is going to be Grass_LayerInfo, we leave it as default.
And then suddenly, our map becomes all grassy.
We repeat the step for the dirt, it's name will be Dirt_LayerInfo

Now this landscape is way too shiny, so we are going to set a specific roughness.
We do left click while holding 1 to create a single value, and then set it to 1 for maximum roughness.
then we save and build, but now we need to add a normal map to it.
We go to the textures folder and find T_Ground_Grass_N
then we find the one for rust which is T_Metal_Rust_N
We are going to do the same thing for the normal maps we did for the textures, so we'ro going to do a duplicate of the layer blend.
for that we use ctrl + D and then we connect the normal maps to the layer blend, using the RGB output to the input.
Then we connect the layerblend to the main node.
Now we can paint and easily switch between the grass texture and the rust texture.
Now we want a human reference to be able to gauge the tiling and just the size of everything.
We go into the content drawer, then in the top left corner there is an Add button (Green plus with Add word) and inside we select
Add > Add a feature or content pack
select the third person, and then click on Add to project.
This will open the content drawer at
All > Content > ThirdPerson > Blueprints
Now we go to All > Content > Characters > Meshes
and we take SKM_Manny and drag it into our map. Now there could be some loading while you do that, don't worry just wait for it to end.
By looking at the feet of Many, we can see that the grass texture is a bit too small, so we are going to fix that.
we're going to need the same size scaler that we had for the master material, so we are going to simply go into its graph and copy paste the 3 nodes that we want.
We are going to plug the output of the multiply to the input of grass texture, and also to the grass normal map. For both of them the input is UV.

But now, for this new setting to appear, we need to creat a new instance of our material.
Its name is M_Landscape_Inst (the default name for a new instance).
We then replace the former material with this one by putting it into the material selection for the landscape in the landscape details.
Now we can have the main viewport and the instance both open at the same time, and check the size box, and now we can see it change in real time.
To increase the texture size, we need to actually go to the left of the slider, because it will decrease the scale.
The change works in real time, if we set it to 0.9 we see the change immediately.
Let's put it to 0.3, we can clearly see that it looks better that way.
Let's do the very same for the dirt now, copy the 3 nodes. Note that the graph wouldn't appear in an instance, we have to select the material itself.
Now the problem with this is that now the size slider controls both the grass and the dirt simultaneously, and we want to control them independently.
That's because the material name is exactly the same and so it is merged into the instance. To avoid that, we simply give the parameters a different name.
Let's set the name in the details of the node on the left.
For the dirt, we only need 1.3 and we're good, it works.
