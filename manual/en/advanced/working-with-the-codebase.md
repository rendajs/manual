# Working With the Codebase

Assuming that you have already
[set up your development environment](./building-from-source.md), here are some
tips for getting around the codebase.

## Documentation and Readme's

Many files contain a quick overview in a comment at the top of what the file
does. These comments either contain a `@fileoverview` JSDoc tag, or in the case
of some classes, there might be some JSDoc comments directly above the
constructor.

Some folders also contain `readme.md` files with an overview of all of the files
in that directory. These readme files tell you how a collection of multiple
files work together as a single system.

If you ever run across files that are missing documentation, or if there is
anything you don't understand, please ask around! If you find that the
documentation is a bit lacking, you can even open up new issues to ask for
clarification. Most likely a readme file or a JSDoc comment simply hasn't been
added yet.

## Quick Overview

The main two folders that contain the majority of code are `src/` and `studio/`.

- `studio/` contains all first-party code needed for running
  [renda.studio](https://renda.studio).
- `src/` contains the engine itself. The engine is what is bundled with
  applications built by Renda Studio. It can also be used as a standalone
  library, without the help of Renda Studio. The engine is also used by Renda
  Studio to render entities, among other things.

## Editing Code Without Reloading

If you want to modify JavaScript files without the need to reload the page, you
can make use of the Workspaces feature in Chrome DevTools.
[This page](https://developer.chrome.com/docs/devtools/workspaces/#devtools)
tells you all about it, but here's the gist of it:

1. Open the **Sources panel** in DevTools.
1. In the left sidebar of the Sources panel, click the **Filesystem tab**.
1. Click **Add folder to workspace** and select the `Renda` repository directory
   in the file picker that opened.
1. When prompted, click **Allow**.

And that's it! You should be able to modify JavaScript files from your favorite
editor or from DevTools directly.

NOTE: There are some circumstances where you still need to reload after editing.
Though DevTools will almost always print a warning in the console when this
happens.

## The Console Is Your Friend

While in development, you can make use of the browser inspector to debug
application state. For some situations, you might have to add breakpoints, but
more often than not you might be able to access some application state via the
`studio` global variable.

One such example is `studio.selected`, here you can access your current
selection. If you click an entity in the outliner for example, you'll be able to
access all children, parents, and components of that entity.

Another useful example is `studio.windowManager.lastFocusedContentWindow`, which
gives you access to, you guessed it, your last focused content window. This is
useful when making changes to the UI of a specific window. For example, you can
click the entity editor window and then access its camera via
`studio.windowManager.lastFocusedContentWindow.editorCamera`.

WARNING:

The `studio` global should not be used inside production code, it is only useful
when you want to debug things.

If you need access to the studio instance from within the code, it's best to
make use of dependency injection. All `ContentWindow`s have a `studioInstance`
property for instance.

But sometimes dependency injection is not ideal, in those cases, you can make
use of `getStudioInstance()`.

END WARNING
