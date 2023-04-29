# Create a Master Material

We are going to create a master material, it feels as if it might be a parent class that will make handling the children class more easily.

We are renaming our spanish pavement into M_masterMaterial.

First of all, we want to make this parent very generic, and for that we are going to make sure that the default values for the parameters don't change anything for the properties. For instance, if the default value for a skeleton is purple instead of white because of the parameter, then we need to arrange the default value of the parameter so that it leaves the skeleton white.

Normal flatness at 0 is good, Roughness strength at 1 is good, color tint should be pure white, let's fix it.

The multiply node related to the coordinate and the size is off, so we need to adjust it.

it was at 0.5 for me, 0.35 for the tutorial, we need to set it to 1 so that it doesn't change anything.

Now everything is back to default, let's make it so we can swap textures on the fly too.
For that, we're going to go on a texture, and convert it to a parameter.
We'll do that for Roughness, Normal, and Color.

With these parameters, we can now go select any texture by clicking once left click on them, and click on the arrow that looks left inside the detail of the instance, and we can go crazy, I selected some weird red purple texture with the normal map of the bush.

after setting everything back to default, we're going to edit the master material again and edit the metallic property to set it as a parameter.

We're going to duplicate the roughness parameter, rename it to metallic, and then add a switch. The output of the metallic goes into the input true of the switch. Then we create a scalar1 value and set it at 0, and we connect the output of this scalar value to the input false of the switch.

That way, since we don't want every class to have a metallic value (even set to 0) as long as we don't want them to be metallic, then if false the property is tured of and it gets rid of the metallic map, it doesn't use the roughness texture.

Be careful, we need to make a switch PARAMETER, not the function.

now we have our master material that we can use for various things.
