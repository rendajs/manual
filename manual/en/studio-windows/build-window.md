# Build Window

The build window allows you to run your application from within Studio itself.

## Adding entry points

Before you can run your application, you first have to let the build window know
where the entry point of your application is. To add an entry point, follow
these steps:

1. Click the **Entry Point** button at the top of the build window.
2. Drag an asset that can function as an entry point (at the moment this can be
   either a `.js` or a `.html`/`.html` file) from the **Project Window** to the
   droppable gui.
3. Click the **+** button next to the droppable gui.

If this is your first entry point, you will now see a single button. Otherwise,
you'll see a list of previously added entry points and you can choose the one
you'd like to use.

## Running

To load your page, click the play button. This loads your entry point inside an
iframe. When running, two new buttons appear that allow you to either remove the
iframe or reload it.
