# Entity Editor

The entity editor is where all the magic happens. Naturally, it is also the most
visually interesting window inside Renda Studio. The entity editor is what
allows you to move around entities, or make adjustments to properties while
instantly seeing the updated changes.

## Navigating the Editor

When you are using a touchpad that supports two-finger scrolling, you can use
that to control the camera.

By default, this gesture orbits the camera, but there are a few modifier keys
that you can use to control the behavior of the gesture:

- `Shift` allows you to pan the camera, i.e. left, right, up, and down in a
  straight line, without rotating.
- `Ctrl` or `⌘` allows you to move the camera forwards and backward. Depending
  on your browser and platform, you might also be able to use pinch gestures on
  your touchpad to move the camera this way.

NOTE: Moving the camera while holding down a mouse button is not yet supported,
but [it is planned](https://github.com/rendajs/Renda/issues/544).

## Moving Entities

In the top left of the entity editor are three buttons that allow you to switch
between different transformation modes. These buttons allow you to
**Translate**, **Rotate**, and **Scale** entities respectively.

NOTE: Scaling is
[not yet implemented](https://github.com/rendajs/Renda/issues/351).

Once you have picked your transformation mode, the gizmo of your selected entity
should change accordingly. You can drag this gizmo around the scene to move the
selected entity.

You can also use the `G`, `R`, and `S` keys to switch transformation modes.
However, this will immediately initiate the dragging action. To stop dragging,
click the entity editor.

Alternatively, you can keep holding these keys down and move your mouse without
clicking. This will keep dragging the entity as long as you hold the key.

## Controlling the Space and Pivot of Your Gizmos

Next to the transformation modes buttons are two extra buttons. These control
the transformation space and transformation pivot.

The first button controls the **orientation** of your gizmo. When a gizmo is
oriented differently, it affects the direction of movement when you move only a
single axis.

There are two orientation modes:

- **global** causes the gizmo to be aligned with the axis of your world. It will
  always be oriented the same, regardless of how your entity is oriented.
- **local** causes the gizmo to have the same orientation as your entity.

The second button has no effect with only a single selected entity. But when you
have multiple selected entities, it controls the **position(s)** of your
gizmo(s). It has three modes:

- **center** places a single gizmo at the average location of all your selected
  entities.
- **multiple** places an individual gizmo at every selected entity.
- **last** places a single gizmo at the location of your last selected entity.

The position of a gizmo does not affect translation gizmos, but for rotation and
scale gizmos it controls the pivot around which an entity is rotated or scaled.
