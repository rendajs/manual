# History Graph

The history graph shows the changes you have made in the past. It allows you to
undo and redo previous actions.

NOTE: Keyboard shortcuts for history are
[not yet supported](https://github.com/rendajs/Renda/issues/549).

Your previous actions show up in chronological order from top to bottom.
Clicking one of these entries makes the state of your project go back to when
that action was performed.

In a lot of software, it is possible to lose a lot of progress by going far back
in your history and then making a change. That's because usually when you make a
change, that overwrites any of the undo's that you have done.

But in Renda Studio it is completely fine to do this. The history graph will
simply create a branch for your new changes. You can go back to entries in your
old branch at any time simply by clicking them.

If you're already familiar with Git branches, this history graph might seem
familiar. But while the history graph may _look_ like a Git graph. It is
actually completely unrelated and has no idea about the state of Git in your
project.

WARNING:

When you reload the project, your history will be lost!

The timeline is only retained in memory, so when you open another project or you
reload the page, the timeline will be emptied.

Since most changes in Renda are autosaved, undo and redo actions are usually
instantly saved as well. Therefore it is recommended that you use some form of
version control like Git or SVN to track the changes in your project.

END WARNING
