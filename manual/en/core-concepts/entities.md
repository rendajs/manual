# Entities

Entities are the main building block of a Renda scene. In fact, even scenes are
entities themselves.

If you have worked with other engines before, you are likely already familiar
with entities. In other software, these are usually called GameObject, Object3D,
or Group among other things.

## Hierarchy

Entities can be nested and form a hierarchy. This allows you to group multiple
entities together to keep things organized. You can then move all those grouped
entities at once by moving the parent.
[The outliner](../studio-windows/outliner.md) shows the current hierarchy and
allows you to modify it.

## Entity Assets

Since Renda has no concept of scenes, you might be wondering where you should
store your entity hierarchy in your projects. This is where entity assets come
into play. An entity asset stores a root entity along with all of its children.
There are two ways to create a new entity asset:

- In the **Project Window**, you can click the **+** button and choose **New
  Entity**. You can then double-click the created entity to open it, and then
  start editing.
- Or you can drag the root entity from the **Outliner** to a folder in the
  **Project Window**.

A project can contain multiple entity assets, each representing a scene.

## Linked Entity Assets

But entity assets can be used for more than just scenes. They can also serve as
reusable objects. That way, whenever you make a change to your entity asset, it
will instantly be updated everywhere else as well.

Creating a linked entity asset is easy:

1. In the **Project Window**, click the **+** button and choose **New Entity**.
2. Drag the created entity asset to your **Outliner Window** and drop it to
   create a new child.

When doing this, the created child is shown with a link icon next to its name.
This icon means it is an entity asset. Making changes to it or any of its
children will instantly be applied to other entities that reference it.

You can try this out right now! Simply drag the same entity asset to your
**Outliner** again. You should now see two child entities, both with a link
icon. Now go ahead and select one of those entities and make some changes to it.
You can rename it or add a new child for example. The moment you do this you
should see the other entity get updated as well.
