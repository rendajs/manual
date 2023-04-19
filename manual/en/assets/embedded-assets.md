# Embedded Assets

When dealing with custom shaders for materials, it is not uncommon to end up
with a lot of different assets with only a small amount of content. To create a
material with a custom WebGPU shader, for example, you'll likely end up with:

- A material, containing all the properties.
- A material map, in case other plugins or renderers need the material as well.
- A WebGPU pipeline configuration, describing how the material should be
  rendered.
- And finally a vertex and fragment shader.

This is all a bit much, especially since, more often than not, you don't even
use multiple renderers or plugins.

So to make the project a little less cluttered, you can combine the first three
of these into one single asset. This can be done using embedded assets:

1. Locate a [droppable GUI](../interface/droppable-gui.md) for which you want to
   create an embedded asset. In the example above, this would be the **Material
   Map** field in the **Properties Window** of a material asset.
2. Right-click the droppable GUI, and from the context menu choose **Create
   Embedded Asset**.
3. Double-click the droppable GUI to open the created asset.

These steps create an embedded asset inside the material asset. You can perform
the same steps for the Forward Pipeline Configuration as well.

If you're curious, you can open the material asset in a text editor and compare
the differences to a material without an embedded asset. You'll see that the
UUID of the linked asset has been replaced with the asset data of the embedded
asset.

So instead of this:

```json
{
	"assetType": "renda:material",
	"asset": {
		"map": "873ade41-8986-4371-b2a3-5bc1aff9d938",
		"properties": {
			"metallicAdjust": 0.123
		}
	}
}
```

You will see this:

```json
{
	"assetType": "renda:material",
	"asset": {
		"map": {
			// map asset data here
		},
		"properties": {
			"metallicAdjust": 0.123
		}
	}
}
```

NOTE:

It is
[not possible to extract embedded assets](https://github.com/rendajs/Renda/issues/568)
yet. If you'd like to turn your embedded assets into a standalone asset inside
your project folder, you can do so by manually taking the asset data from the
JSON file.

When doing so, be sure to wrap the asset data with the appropriate `"assetType"`
data. It might be easier to create a new asset from within Renda first, and then
replace its contents using a text editor.
