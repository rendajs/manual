# Default Asset Links

Imagine a situation: You have carefully created a large scene with tons of
objects in it. You haven't put a lot of thought into the materials yet, so
everything still uses the default material. But now you need to replace all of
those materials with a custom one, maybe you'd like some custom shading, or
perhaps a plugin requires it.

This might seem like a daunting task, but do not worry, default asset links to
the rescue!

Default asset links allow you to 'link' from many places to one asset, similar
to how symbolic links or website redirects work. Essentially what this means, is
that you can drag and drop asset links to places where you would normally drop
an asset. You can then change what this asset link points to at any time.

If you are reusing the same asset many times across your project, it is advised
to create an asset link for it. Because then you only have to change what the
asset link points to once, and it will update everywhere across your project.

## Creating Default Asset Links

Let's go over how to create a new default asset link for your project.

1. Open the **Default Asset Links Window**.
2. Click the **+** button to create a new entry.
3. Give your default asset link a name using the first field. This is the name
   that will appear across your project. But don't worry, you can change this at
   any time.
4. Drag an asset from the **Project Window** to the second field.

And that's it, you can now drag the item from the third field to anywhere inside
your project. If you ever need to change its name or what asset it points to,
you can do so at any moment and all references in your project will
automatically update.

## How it works

When you create a default asset link, a [new asset UUID](../assets#asset-uuids)
is created, this UUID can then be used across the project just like any other
asset. Whenever an asset needs to be loaded, it is resolved to the actual asset
instead.

However, when you build your application, all these links are lost. Instead, the
resolved UUIDs will be bundled and used inside the build. This prevents some
unnecessary overhead since asset links are mostly useful during development
anyway.

## Built-in Default Asset Links

Apart from the default asset links that you can create yourself, there are also
some built-in default asset links. These don't have a name field, and point to a
[built-in asset](./built-in-assets.md) by default.

Whenever you create something new, fields usually have these built-in asset
links as default values. If you create a new mesh component, for example, the
material field starts with the 'Default Material' selected. This 'Default
Material' is a built-in default asset link that you can replace with your own
custom material. That way, any newly created mesh components automatically point
to your custom material. Neat!

Another useful result of this is, that you can share your assets online, or
import assets from someone else. If they have made clever use of these built-in
default asset links, you won't even have to modify anything. The imported asset
should automatically point to the assets you have already configured!

It is not possible to remove built-in default asset links. You can unlink them
if you like, but there is generally very little reason to do so. All the default
asset links will be lost when building, so unlinking won't make your build size
decrease.

Similarly, it will not make your project files smaller either. Built-in asset
links that still have their default value are not stored inside your project. So
unlinking them will actually make your project bigger.
