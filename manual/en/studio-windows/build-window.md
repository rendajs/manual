# Build Window

The build window allows you to run your application from within Studio itself.
Renda uses an iframe to display your application, but this does not mean that an
internet connection is required to display the contents of the iframe. The
contents of your project never leave your device in this case.

NOTE: You still need an internet connection to load the page
[for now](https://github.com/rendajs/Renda/issues/560). But once Renda Studio
has loaded, no more data is transferred to an online service.

## Adding entry points

Before you can run your application, you first have to let the build window know
where the entry point of your application is. To add an entry point, follow
these steps:

1. Click the **Entry Point** button at the top of the build window.
2. Drag an asset that can function as an entry point (at the moment this can be
   either a `.js` or a `.html`/`.htm` file) from the **Project Window** to the
   droppable GUI.
3. Click the **+** button next to the droppable GUI.

If this is your first entry point, you will now see a single button. Otherwise,
you'll see a list of previously added entry points and you can choose the one
you'd like to use.

If you selected an HTML file as the entry point, the contents of that file will
be directly loaded inside the iframe. You can put anything you like inside the
HTML file. You can even choose to never load Renda inside this file and just
serve something completely unrelated.

JavaScript assets, however, can not directly be displayed inside the iframe.
Therefore they are loaded with a small wrapper HTML file. This HTML file
contains a few utilities to make it easier to work with Renda, such as an import
map so that you can `import from "renda"` or `"renda:services"` inside your
scripts. But other than that, the HTML file only contains a script tag that
loads your selected entry point.

## Running

To load your page, click the play button. This loads the currently selected
entry point inside the iframe. When running, two new buttons appear that allow
you to either remove the iframe or reload it.
