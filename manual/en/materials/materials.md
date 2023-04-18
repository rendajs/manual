# Materials

Materials allow you to configure how meshes are being rendered to the screen.
With materials you can choose the color of objects, what textures they use, and
much more.

If you followed the steps in
[Your First Sphere](../getting-started/your-first-sphere.md), you may have
noticed the **Materials** section inside mesh components. This is where you can
drop material assets to let the renderer know what material a mesh should be
displayed with.

## Creating a Material

When you create a new mesh component, the **Default Material** is automatically
assigned. The default material is rather bland though, and because it is a
[built-in asset](../assets/built-in-assets.md), you can't change it. So if you'd
like to change the looks of a mesh, you'll have to create a new material asset
first:

1. In the **Project Window**, click **+** to open a context menu.
2. Choose **Materials**, then **New Material** to create a new material asset.
3. Drag the newly created material to your mesh component to apply it.

You may not see much of a difference yet, that is because the created material
has the same values as the default material. Let's do something about that!

1. Click the material you just created in the **Project Window**
2. In the **Properties Window**, try to change the value for **Roughness
   Adjust**.

Your mesh should now visibly have different shading. Feel free to play around
with different properties for a bit to see what they do. Or head over to
[Default Material Map Properties](./default-material-map-properties.md) for an
explanation.

There is only so much the default material map can do though. If you want more
control over things such as transparency or toon shaders, you'll have to select
a different material map. At the top of the properties window is a droppable GUI
that allows you to link a material map asset.

The plan is to eventually build up a collection of
[default material map assets](../assets/built-in-assets.md), but for the time
being, only the default material map exists. If you'd still like to gain more
control over your materials, you could have a go at creating your own material
map. This could get a bit advanced, but if you're up for a challenge, head over
to [Material Maps](./material-maps.md).
