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
