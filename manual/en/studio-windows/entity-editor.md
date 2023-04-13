# Entity Editor

The entity editor is where all the magic happens. Naturally it is also the most
visualy interesting content window inside Renda Studio. The entity editor is
what allows you to move around entities, or make adjustments to properties while
instantly seeing the updated changes.

## Navigating the Editor

When you are using a touchpad that supports two finger scrolling, you can use
that to controll the camera.

By default, the camera orbits around when dragging like this, but there are a
few modifier keys that you can use to control the behaviour of the camera:

- `Shift` allows you to pan the camera, i.e. left, right, up, and down in a
  straight line, without rotating.
- `Ctrl` or `⌘` allows you to move the camera forwards and backwards. Depending
  on your browser and platform, you might also be able to use pinch gestures on
  your touchpad to move the camera this way.

Moving the camera while holding down a mouse button is not yet supported, but
[it is planned](https://github.com/rendajs/Renda/issues/544).

## Moving Entities

In the top left of the entity editor are three buttons that allows you to switch
between different transformation modes. These buttons allow you to
**Translate**, **Rotate**, and **Scale** Entities respectively.

NOTE: Scaling is
[not yet implemented](https://github.com/rendajs/Renda/issues/351).

Once you have picked your transformation mode, the gizmo of your selected entity
should change accordingly. You can drag this gizmo in order to move your entity.

You can also use the `G`, `R`, and `S` keys to switch transformation modes.
However, this will immediately initiate the dragging action. To stop dragging,
click the entity editor.

Alternatively, you can keep holding these keys down and drag your entity. The
dragging will then stop the moment you release the key.

## Controlling the Space and Pivot of Your Gizmos

Next to the transformation modes buttons are two extra buttons. These are the
transformation space and transformation pivot buttons.

The first button controls the **orientation** of your gizmo. It has two modes:

- **global** causes the gizmo to be aligned with the axis of your world. It will
  always be oriented the same, regardless of how your entity is oriented.
- **local** causes the gizmo to have the exact same orientation as your entity.

The second button has no effect with only a single selected entity. But when you
have multiple selected entities, it controls the **position(s)** of your
gizmo(s). It has three modes:

- **center** places a single gizmo at the average location of all your selected
  entities.
- **multiple** places an individual gizmo at every selected entity.
- **last** places a single gizmo at the location of your last selected entity.

NOTE:

With multiple selected entities, the locations of the gizmos have an effect on
how all of your entities are moved.

For example, if you set the **orientation** to **local** and the **pivot** to
**multiple**, then every entity will move according to their own local gizmo. In
that case, one entity might be moving up when you drag the y-axis, but if
another entity is oriented differently, it might move in a completely different
direction.

END NOTE
