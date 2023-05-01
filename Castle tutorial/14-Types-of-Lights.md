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
