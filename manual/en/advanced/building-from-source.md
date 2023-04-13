# Building from Source

If you'd like to contribute code to Renda Studio or its engine, you'll likely
want to try out the changes locally before submitting a PR. Fortunately, Renda
does not need a build step in order to run! So in theory checking out the code
and starting a server should be enough.

## Running Studio Locally

In practice though, Renda Studio still has a few dependencies that need to be
downloaded. Follow these steps to get started:

1. [Install Deno](https://deno.land/manual/getting_started/installation)
1. Run `https://github.com/rendajs/Renda.git` to check out Renda's main
   repository.
1. cd into the cloned repository with `cd Renda`
1. Run `deno task dev` to install dependencies and spin up a development server.

If this is your first time running this command, it will download some required
dependencies, though this generally shouldn't take too long. Once that's done,
it starts a server with all the files at http://localhost:8080, Renda Studio can
be found at http://localhost:8080/studio/.

Other than starting up a basic HTTP server, this task also comes with some
useful utilities. For example, it hosts a WebSocket that allows you to modify
Built-in assets right from Studio. This way you can modify Built-in shaders
outside of your browser and directly see updates without the need to reload the
page.

Once the server has started, this command will start downloading and generating
some files in the background that allows you to get type checking and
autocompletions in your editor. This even works for files touching Deno code, no
Deno extension required!

### Editing Code Without Refreshing

If you want to modify JavaScript files without the need to reload the page, you
can make use of the Workspaces feature in Chrome DevTools.
[This page](https://developer.chrome.com/docs/devtools/workspaces/#devtools)
tells you all about it, but here's the gist of it:

1. Open the **Sources panel** in DevTools.
1. In the left sidebar of the Sources panel click the **Filesystem tab**.
1. Click **Add folder to workspace** and select the `Renda` repository directory
   in the file picker that opened.
1. When prompted, click _Allow_*.

And that's it! You should be able to modify JavaScript files from your favorite
editor or from DevTools directly.

NOTE: Note that there are some circumstances where you still need to reload
after editing. Though DevTools will almost always print a warning in the console
when this happens.

## Actually Building From Source for Real Now

Ok but let's be honest, downloading all these separate source files in the
browser every time you load the page is not very efficient. That's why the
version hosted on [renda.studio](https://renda.studio/) has a bundled version of
all the JavaScript and CSS files.

If you wish to build Studio you can run `deno task build-studio`. This will
place all the files in `studio/dist/`. You can view the built version by going
to http://localhost:8080/studio/dist/ in your browser. Similarly, you can run
`deno task build-engine` to build only the engine.

But if you like to contribute code, none of this is even necessary! Every PR
automatically builds the code for you and deploys it to
`https://pr-${PR_ID}.renda.studio/`. But since you can make changes and try them
out locally without building, it's unlikely that you'll ever need to run this
task.
