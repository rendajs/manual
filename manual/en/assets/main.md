# Assets

Projects consist of many different assets, and the majority of assets will be
located inside your project folder.

To view which assets are contained inside your project, have a look at the
[project window](../studio-windows/project-window.md). These are all the assets
that you can modify and then reuse accross different locations inside your
project. A [material asset](../materials/), for instance, can be reused for
multiple meshes in your scene.

Other than in your project folder, assets can also be found inside the
[built-in assets window](./built-in-assets.md), or inside other assets
themselves as [embedded assets](./embedded-assets.md).

## Asset UUIDs

TODO

## Different Asset Types

There are many different types of assets, too many to name here in fact. But
several assets have some things in common, so we'll talk about that instead.

The most common type of asset you will see are in `.json` format. They can
easily be inspected within either Renda Studio, or you can try to edit the raw
file with any text editor. Some examples include: materials, vertex state, or
sampler assets.

Other assets like images or audio files are usually more efficient to store in a
binary format. These might not be as easy to view in a text editor, though you
can usually edit them with external tools. One exception are `.rmesh` files,
though there is some limited functionality for editing these inside Renda
Studio.

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

Finally there's one last form that assets can be in, though normally you won't
have to deal with this too much. JSON files are an easy format for you as a
developer to work with, but when it comes to users downloading your application,
you want the assets to be as small as possible. That's why assets take one final
form when being bundled.

Bundled assets are not meant to be inspected so they are stored in a binary
format. When you bundle your assets, they get serialized into binary, and when
your application loads they get deserialized again into instances like the
`new Material()` mentioned earlier.

## Responding to External Changes

TODO - Explain asset watching and updates inside renda studio
