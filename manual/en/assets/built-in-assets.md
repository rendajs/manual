# Built-in Assets

Some types of assets are almost always needed in any project, such as the
default material for example. Others may not be directly used by you but are
still loaded by Renda to make things work right, one example would be some
shaders utilities used by the WebGPU renderer.

To make this possible, Renda has a collection of built-in assets. These assets
can be found in the **Built-in Assets window**.

Assets in this window work in a very similar way to the assets inside your
project folder, with the only exception being that they can't be edited. But
they can still be dragged to [droppable GUIs](../interface/droppable-gui.md),
are bundled alongside the assets from your project folder, and contain asset
UUIDs just like your assets.

Built-in assets often come with an accompanying
[default asset link](./default-asset-links.md), so if you plan on using a
built-in asset, you might want to check if there's a default asset link that you
can use instead.
