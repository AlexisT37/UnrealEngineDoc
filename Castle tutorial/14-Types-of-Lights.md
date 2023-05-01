# Types of Lights

Let's start by deleting our point light.
Of course, once that happens, the level becomes surrounded in darkness.

We start by getting a Point Light from the Add object option(cube with green plus),

It is very basic, it emmits light in all directions.
The most important setting right now is intensity of the light.

In the details, it is intensity and the default value is 8.0 cd

cd is a real unit of light, it is the candella.
0 means no light at all, and we get insanely bright very quickly.

We are going to set on 4, witch feels just right for me.
We can change the source radius, wich makes the shadows less sharp, but if we increase it with game view turned off (G), it changes the outline of a yellow sphere, this sphere is not visible with game view turned on.

The default value vas 0, and there we have harsh shadows, but they become softer as we increase the value as the lighting looks more like a sphere than a point, therefore the rays don't come from one place which explain the softer shadows.

Let's set it to 20.

We can also choose to use the temperature parameter of the light, as a reminder the temperature is red for warm, blue for cold.
Light > Use Temperature is unchecked by default you can check it

Default is 6 500, lowest value is the warmest at 1 700, highest value is 12 000 and is the most blue.
We'll set temperature to uncheckd for now.

Let's move on with the light color

it of course gives us a color picker to change the color of our light.

We put it back at white, and then check the indirect lighting intensity, whose base value is 1.0
if we set it to 0, then we have no bounce and the light looks just like at the beginnig.

the room quickly becomes super bright if we increase the value, because it keeps bouncing and bouncing.

Now we are going to delete our point light and create a new type of light, the spot light.

The spot light is a cone, and we have a wireframe to help with the angle.

You can change the direction the light is pointing by rotating it.

We have two new settings, the inner cone angle and the outer cone angle.

This is because there is two levels of the lighting, and there is a falloff, a smoother edge to the lighting, if the outer cone has a larger radius.
If the outer cones get lower and lower, it will eventually bring down the inner cone with it, and that just gives a smaller cone overall. Also once the inner cone and the outer cone have the same radius value, then the cone is very sharp.

Let's delete that and go into the rectangle light.

Now we are similar to the spotlight except we are emmiting for a rectange in a specific direction, much like a tv or a projector like in kindom hearts gummi ship

Notice that you can't scale this object.

However, I can increase the size of the rectangle by increasing the width.
Source width and source height for the size, then there is the parameter of the barn door angle and the barn door length.
The barn angle extends the light like a fan, and the length makes the surrounding of the light, just like horse blindes, larger.
The larger the barn, the larger the surrounding shadow around the light source.

Now we move on to the most used light, the directional light.
At first we don't see anything, because it is the sunligth and we have to move it and rotate it to see the effect.
It is very bright, and pointed in a specific direction infinitely.

You can change the source angle to control the edges of the shadows, lower values for smoother edges, higher values for smoother shadows.
