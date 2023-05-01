# Lighting with Lumen

It is very good because it gives us real time global illumination.

Global illumination is what gives the fidelity to true lighting, but the problem is that it is very expensive to calculate.
Lumen is so good because it allows to give good lighting to a fraction of the cost of raytracing for example.

We're now going to use the content we just migrated !

go to the level All > Content > LightingExamples > Maps > Lightbounce

It's a small cube level in the dark with a green side on the left, a red side on the right,
a long vertical yellow cylinder on the left and a white sphere on the ground on the right.

The light seems to come from some point in the middle up-left of the room.

We will start by showing how illumination worked before lumen, and for that we need to turn off lumen.

We go to the PostProcessingvolume, and to the details > Global Ilumination > Method, and if Lumen is selected select None instead.

Method is none by default, and if you try to switch to lumen it will ask you to rebuild, maybe we will see that later.

With none, we can see that the shadows are very dark, and it doesn't look realistic (Although I didn't notice that at first).

Go to the PointLight item, to the details, and then Transform > Mobility
and the Mobility should be Static, not Mobile.

We're lucky, we are going to use the Build menu with the option Build all Levels, which will probably the message to rebuild in red. Few !

there was an error at first but then it went away, and now we have a shadow render that is a bit more realistic.

Interestingly enough, UnrealSensei also had the same error, but just like for me it is gone.

We can see that indeed the shadow is not pitch black, but also the color is bouncing from the colored surface, there is a little bit of red on the ball, and there is a bit of green on the yellow cylinder.

There are major issues with this process, namely all shadows are static, so if we move the sphere then the shadows stays there.

If we move the light away, it also changes everything, there is the moving shadow made by the light, but also the static shadow that was generated.

This is why lumen is so good, it gives us the ability to have dynamic global illumination.

To do that, let's first git rid of the light map wich was created with the build.

Sometimes there is a world Settings tab, but not here, so we need to go to the Window menu on the top left, and then click on World Settings in the dropdown menu.
It's in the LEVEL EDITOR part, the last option right above the LOG part.

Note that this doesn't open a new window, it adds a new tab next to the details.

Before tweaking the settings, we get rid of the light map
Lightmass > Advanced > Force No Precomputed Lighting should be check, it was unchecked.

There is a warding message, we select ok.

Don't forget to rebuild the level.

Now the good lighting is gone and there is only the pitch black shadows.

We go to the PointLight details and we set the Mobility to Movable instead of Static.

If we move the light, there are only the pitch black shadows that are moving.

We can see that if the reflection uses lumen, the lighting does not. Let's use lumen for lighting now.

Go back to the post process volume details, Global Illumination, and in the method select Lumen.

And now, without rebuilding, we have a perfectly good lighting that is dynamic, softer, and with the right color bounces.

This is something that is totally amazing and was not possible with Unreal Engine 4.

We can adjust the settings, for instance going to the PointLight details and then Light > Source Radius, if we increase it from 0 to 40, we get a much smoother shadow, which is even more realistic.

Another awsome new addition that was not possible with UE4 is that now you can apply lighting to a material, so we can make our ball a source of light.

All > Content > LightingExamples > Materials > M_Emmisive_Inst

This makes the surface emmit light, it works on the sphere, the cylinder, or anything.
