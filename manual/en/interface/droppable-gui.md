# Droppable GUI

A droppable GUI is a location where references to assets can be linked. These
references can then be used by scripts or things like the renderer for instance.
For example, the mesh component allows you to link a mesh and a material. That
way these assets can be reused in other places as well.

## Linking Assets

There are several ways to link an asset but perhaps the most intuitive way is to
drag and drop your asset on top of the droppable GUI.

Alternatively, you can also paste asset UUIDs. For this you need to click the
droppable GUI once. When it receives a blue highlight ring you can paste the
UUID via the `Ctrl` + `V` or `⌘` + `V` shortcut. It is also possible to paste
UUIDs via the right-click context menu.

## Unlinking Assets

To unlink an asset, you can click the droppable GUI and use the `Delete`
shortcut once it receives the blue highlight ring. Again, it's also possible to
do this from the right-click context menu.

## Inspecting Dropped Assets

If you double-click the droppable GUI, the currently dropped asset will be
opened in the properties window. This allows you to quickly view and change
values of the linked asset. This is also the only way to
[edit embedded assets](../assets/embedded-assets.md).

## Finding Out Where an Asset Is Located

If you see a droppable GUI with a linked asset, but you're not sure where this
asset lives in your project, you can right-click the droppable GUI and choose
**View Location** from the context menu.

This will focus either the project window, the built-in assets window, or the
default asset links window and then highlight the relevant asset.

NOTE: Highlighting default asset links
[has not been added yet](https://github.com/rendajs/Renda/issues/554).
