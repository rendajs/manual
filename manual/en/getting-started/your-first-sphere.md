# Your First Sphere

At this point, you should have [renda.studio](https://renda.studio/) open in
your browser. When you start Studio for the first time, you will be greeted with
its splash screen. You can dismiss it by either clicking the **New Project**
button or clicking outside of the splash screen.

NOTE: If you have already opened and edited a project before, by default this
splash screen won't show up. You can click the **Open Project** button inside
the **Project Window** if you want to open it again. More about this later.

## Studio Windows

First let's take a quick glance at how windows work. Renda Studio is divided
into several windows. Each window has an icon in the top left corner. And you
can recognize what type of window something by their icon.

If the icon seems a bit mysterious to you, you can also hover over it with your
mouse and get a tooltip that tells you the name of the window type.

## Creating an Entity

Entities are the main building block of a scene. In fact, Renda doesn't even
have any concept of scenes. Every scene is also an entity. So if you want to
create a sphere, you first need an entity that will serve as a scene.

You can do this in the **Project Window** which can be found in the bottom left
of the screen. This window contains all the assets for your current project. But
at the moment it is pretty empty, let's do something about that!

1. Click the **+** button.
2. Choose **New Entity** from the context menu.
3. Optionally give your created asset a name with the `Enter` or `F2` key.

Great, you have created your first asset!

NOTE:

As you may have noticed, this asset has the `.json` extension. Many assets are
basic JSON files with a very simple structure. This makes it easy to modify
files manually as well.

Usually these files have their default values omitted as well. Making it very
easy to read them when authoring new files or comitting changes in Git.

END NOTE

## Opening the Entity

Now let's **double click** the newly created asset. This will open the entity so
that you can make changes to it. When doing this, your entity appears inside the
**Outliner Window**.

The outliner window shows the tree structure of the entity that is currently
open. But since this entity was just created, it only contains a single entry
right now.

Go ahead and add a couple of children to this entity. You can do so by clicking
the **+** at the top of the **Outliner Window**.

NOTE: Entities function as a tree of nodes. This means you can add any number of
child entities to any other entity. Simply select an entity by clicking it, and
use the **+** button again to add a child to the selected entity.

Alright great, you should have a bunch of entities now. Let's try to add the
sphere asset to one of them.

## Linking the Sphere

You may have noticed that if you select certain things, some things change
inside **Properties Window**. The properties window allows you to view and
modify properties of the selected item.

In order to link your sphere asset from earlier, you first need to add a new
**mesh component** to an entity:

1. Click one of your entities in the **Outliner Window**.
2. Inside the **Properties Window**, click **+** in the **Components** section.
3. From the context menu, choose **Mesh**.
4. Drag your mesh asset from earlier to the droppable area next to **Mesh**
   inside the **mesh component**.

NOTE: If you're unsure what components are or how they work, don't worry about
it. We'll cover this later.

Awesome! You should now faintly see a sphere in the center of the world.

## Let There Be Light

The sphere is a bit dark however, and the only reason why we can see it is
because it obscures the grid. So let's add some lights to the scene as well.

1. Select another entity in your **outliner**. If you need more entities, just
   click the **+** button again.
2. Just like before, go to the **Properties Window** and click the **+** button
   in the **Components** section.
3. This time we'll add a light component by clicking **Light** from the context
   menu.

This adds a light to the scene, but it is currently positioned right inside the
sphere, so you can't see it. You'll have to move the light a bit so that it is
located outside the sphere.

You can move entities by dragging the white circle in the scene. Simply grab the
white circle around the light icon and move it outside of the sphere.

## Conclusion

And that's it! You should now have a visible sphere inside your scene. Go ahead
and save your changes if you like by clicking the **Save** button in the
**Entity Editor Window**, otherwise you the entity asset will be empty again
next time you open it.

We rushed a bit through a lot of different topics in this chapter. Otherwise it
would have taken a long time for you to get something exciting on your screen.
We'll cover a the mentioned topics again in more detail later in this manual.
But hopefully this gives you a idea about the basics in Renda Studio.
