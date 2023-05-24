# Triplanar Mapping

Triplanar mapping (also known as "triplanar texturing" or "triplanar projection") is a technique used in 3D graphics to apply textures to complex geometry in a way that minimizes stretching and distortion.

Let me explain it with a simple analogy: Imagine trying to wrap a gift that's not a simple box shape – it's got all kinds of odd angles and curves. You could try to stretch a single piece of wrapping paper over it, but you'd end up with places where the paper is stretched thin and places where it's all bunched up. That's the problem you face when you're trying to apply a 2D texture to a 3D object.

Here's where triplanar mapping comes to the rescue. Instead of trying to wrap the object with one piece of "paper" (or in our case, one texture), you'd apply the texture from three different directions (hence the name "triplanar"). The three projections are usually along the X, Y, and Z axes.

So, in each spot on the object, the engine actually calculates the texture color three times – once for each projection. It then blends these three values together. The blending is weighted towards the direction that's most facing towards the viewer. This results in a texture that's well-suited to complex geometry and doesn't get stretched or distorted as much.

Now, onto Triplanar Sharpness. This parameter controls how sharply the textures from the three projections are blended together.

With a high Triplanar Sharpness value, the transitions between the different projections are more abrupt, which can be useful for textures that need to maintain high detail, like rocky surfaces. However, it can also result in visible seams where the different projections meet.

With a low Triplanar Sharpness value, the transitions are more gradual, creating a smoother blend. This can be useful for more uniform textures, like sand or water, where you don't want abrupt changes. However, it can also lead to a certain amount of blurring of the texture.

Just like with StartOffset and Blend Falloff from our previous discussion, the right value for Triplanar Sharpness depends on the specific visuals you're trying to achieve. You'd typically adjust it by eye until you get the result you're looking for.
