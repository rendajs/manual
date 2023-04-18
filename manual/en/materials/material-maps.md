# Material Maps

3d software often has many use cases or different kinds of renderers. Maybe you
want to export your scene in a specific format, or maybe you found a plugin that
renders your scene in a specific way. All these use cases have different needs
when it comes to materials.

Therefore it is not uncommon for plugins to require specific properties on
materials. An offline renderer might need a sample count setting for a material
for instance, whereas a real-time renderer might not.

Often when exporter plugins or renderers need a specific property, one common
way to do this, is to tell the user to just replace all of their materials with
one provided by the plugin. But if you have a large scene with many materials,
this is less than ideal.

To work around this issue, materials in Renda all require a 'material map'.
Material maps act as a layer between the user and plugins. They 'map' the
properties as seen by the user to those that are required by the plugin.

This way, if you want to try out a new plugin or renderer, you don't have to go
out of your way to replace all the materials in your scene.

Another benefit is that multiple plugins can be used alongside each other,
something that wouldn't normally be feasible because switching all your
materials back and forth simply takes too much time.

## Creating Material Maps

Every material has a droppable GUI at the top where you can select a material
map. Go ahead and create a new material map asset:

1. Go to the **Project Window** and click the **+** button.
2. From the context menu, choose **Materials** and then **New Material Map**.
3. Select the material that you wish to use your material map in.
4. Drag the created material map to the **Material Map** field in the
   **Properties Window**.

NOTE: If you plan on using the material map only once, you might want to make it
an [embedded asset](../assets/embedded-assets.md) instead.

The material map you just created is still empty, so any object using this
material will not be rendered. To verify this, you can open the material map by
[double-clicking](../interface/droppable-gui.md#inspecting-dropped-assets) it.

With the material map open, you can see that it is indeed completely empty, so
let's do something about that. Click **Add Map Type** and choose **WebGPU
Renderer**. Depending on your use case you might want to add other map types as
well. But for now, we'll stick to the WebGPU use case.

Map types are divided into two sections:

- A list of configuration options for that map type. In the case of the map type
  you just created, it only contains a single 'Forward Pipeline Config' option.
- A list of properties and what name you'd like to map them to.

The second section is still empty right now, that's because we haven't selected
a forward pipeline config yet. Explaining how pipeline configs work is out of
scope for this chapter, so for now let's just use the default pipeline config:

1. Open the **Built-in Assets** window.
2. Navigate to **DefaultAssets** -> **Default Material** -> **Default Pipeline
   Configuration.json**.
3. Right-click the default pipeline config and choose **Copy Asset UUID**.
4. Now go back to the **Project Window** and make sure your material map is
   selected.
5. Right-click the droppable GUI next to **Forward Pipeline Config** and choose
   **Paste Asset UUID**.
6. When asked, allow clipboard permission via the prompt.

You should now see a list of mappable properties. Each property allows you to
configure a mapped name for it. The mapped name is the property name that will
be visible inside the material asset.

If you have enabled multiple material map types. You can point multiple
properties to the same value by giving them the same mapped name. So for
instance, the WebGPU Renderer might use 'normalTexture', but maybe an FBX
exporter plugin might use a different name like 'normalMap'. In that scenario,
you could change the mapped name of the FBX material map type so that it points
to 'normalTexture' as well.
