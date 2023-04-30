# Create a Static Mesh

What is a Static Mesh ? It is a 3d object.
By default they are just a collection of vertices and faces in space.
To change how it looks, we need to apply a material to it.
This material will be composed of multiple texture, as we have seen with the spanish tile.
we're importing the WoodCrate.fbx from the Beginner assets that I downloaded from Unreal sensei.
We create a folder named WoodenCrate and start by importing the fbx inside.
We make sure everything is set to default on the import menu, it's a button just click on it once to be sure
then in the drop down menu for Material Import Method select Do Not Create Material
uncheck Import texture
Then click on import, not import all.
If you get the following message
"No smoothing group information was found in this FBX scene.  Please make sure to enable the 'Export Smoothing Groups' option in the FBX Exporter plug-in before exporting the file.  Even for tools that don't support smoothing groups, the FBX Exporter will generate appropriate smoothing data at export-time so that correct vertex normals can be inferred while importing. "
ignore it it's fine.
get into your crate and save it, or from a right click save it.
damn, the size of the crate compared to the UE prop made me realize the prop is actually pretty large.

After having imported the crate, it's time to use a material, and for that we are going to need the help of our master material.
It has everything except the textures, which we will import via the asset drawer.
All > Content > Mystuff > WoodenCrate
put the 5 texture files in there.
WoodCrate_BaseColor srgb was on, we turned it off
WoodCrate_Metallic sgb off because it is a mask
WoodCrate_MetallicRoughnessOcclusion
WoodCrate_Normal, srgb was already off, which is good, also texture group normal map, and compression settings is also normal map
WoodCrate_Roughness srgb was on, we turned it off

Now we right click on the master material, and we create a material instance from it.
MI_WoodenCrate
We move this instance into the WoodenCrate folder.
If we apply the material to the plate, it's obviously going to have the texture of the floor and we don't want that.
we go to edit the material, and activate color, normal and roughness.
We start by dragging the base color, the normal and the roughness into the right texture slots.

we are going to use the metallic parameter that we created in the master material, because there is a metallic element in the crate object (the nails), then we can activate the property and load the metallic nail texture.

The texture we want is WoodCrate_Metallic

Now by using ctrl + L to control the light, we can see that the nails are indeed reflecting the light.

This is very quick and this is why we made the master material, because just like a php class, it allows us to set property more easily.

You can of course change the other properties of the crate according to the master material, for instance I'm going to increase the normal map effect a little bit.

If you want to use a texture and it looks messy, remember that it's probably because the size is not the correct one, which means you need to set it to 1.

Now if we want to duplicate the crate, we notice that duplicates will have the material, but if we do a box from the content drawer, then it won't have the material.

We can go into the crate editor by double clicking and in the editor view, top right, there is a place for the default material.

Details > Material Slots > Element 0
