# Assets

Projects consist of many different assets, the majority of which will be located
inside your project folder.

To view which assets are contained inside your project, have a look at the
[project window](../studio-windows/project-window.md). These are all the assets
that you can modify and then reuse across different locations inside your
project. A [material asset](../materials/), for instance, can be reused for
multiple meshes in your scene.

Other than in your project folder, assets can also be found inside the
[built-in assets window](./built-in-assets.md), or inside other assets
themselves as [embedded assets](./embedded-assets.md).

## Different Asset Types

There are many different types of assets, too many to name here in fact. But
several assets have some things in common, so we'll talk about that instead.

The most common type of assets you will see are in `.json` format. They can
easily be inspected within either Renda Studio, or you can try to edit the raw
file with any text editor. Some examples include materials, vertex state, or
sampler assets.

Usually, these files have their default values omitted inside the JSON file.
This makes it very easy to read them when authoring new files or committing
changes in Git.

Other assets like images or audio files are usually more efficient to store in a
binary format. These might not be as easy to view in a text editor, though you
can usually edit them with external tools. One exception is `.rmesh` files.
Though there is some limited functionality for editing these inside Renda
Studio, the values of individual vertices can't easily be edited.

## Asset Forms

Assets can have different 'forms' (for lack of a better word) in which they are
used.

The most obvious form, as mentioned above, is how it is stored on disk. But
reading files from disk every time you need to render a texture is not very
efficient. That's why, whenever an asset is loaded in an application (or even
when displayed inside the [entity editor](../studio-windows/entity-editor.md)),
the asset is converted to something that can be manipulated more easily.

Let's take a material asset for instance. When stored on disk, it is a basic
JSON file. But when it is going to be used inside an application, it will be
converted to a `new Material()` instance. Most assets will be turned into a
class instance that you can also instantiate yourself. A material for example
can also be instantiated from JavaScript without ever needing to load any
assets.

Finally, there's one last form that assets can be in, though normally you won't
have to deal with this too much. JSON files are an easy format for you as a
developer to work with, but when it comes to users downloading your application,
you want the assets to be as small as possible. That's why assets take one final
form when being bundled.

Bundled assets are not meant to be inspected so they are stored in a binary
format. When you bundle your assets, they get serialized into binary, and when
your application loads they get deserialized again into instances like the
`new Material()` mentioned earlier.

## Responding to External Changes

Renda Studio checks your assets for changes from external applications. This
happens every time Studio receives focus. This way you can make changes to a
shader and quickly see the changes for example.

But this also makes it possible to adjust assets from a text editor, even though
those assets might already be editable within Renda. This allows you to modify
assets with external tools, without the need to reload your project.

## Asset UUIDs

Every asset comes with a unique universal identifier (UUID), which is used for
linking assets together. For instance, a material might want to hold a reference
to a texture, but another material might want to hold a reference to that same
texture as well.

To make this work, assets can store the UUIDs of other assets instead of the
assets themselves. That way, only a small string of text can be stored which
then 'points' to the actual asset.

There are several ways to find out what the UUID of an asset is, though usually,
you won't have to. Knowing the UUID is mostly useful when you want to load a
specific asset from JavaScript, or when you want to inspect the contents of
assets in a text editor.

The easiest way to find out what the UUID of an asset is is to right-click the
asset in the **Project Window** and then choose **Copy Asset UUID**. This copies
the UUID to your clipboard, which you can then paste inside
[droppable GUIs](../interface/droppable-gui.md) or your JavaScript file.

Alternatively, you can open the `/ProjectSettings/assetSettings.json` file of
your project inside a text editor, here you'll see a list of all the asset UUIDs
and the paths they point to.

By default, the UUID of an asset is not persisted. This means that every time
you load the project, it might get a different UUID assigned. But the moment a
UUID becomes referenced somewhere, it becomes persistent. So if an asset is not
listed in the `assetSettings.json` file, it's simply not been used yet. This
keeps the file clean when importing a large number of files, making it easier to
commit your changes in git.
