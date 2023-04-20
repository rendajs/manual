# Entity Editor

The entity editor is where all the magic happens. Naturally, it is also the most
visually interesting window inside Renda Studio. The entity editor is what
allows you to move around entities, or make adjustments to properties while
instantly seeing the updated changes.

## Navigating the Editor

You can drag the viewport by holding down your middle mouse button in the entity
editor. When you are using a touchpad that supports two-finger scrolling, you
can also use that to control the viewport camera.

By default, these gestures orbit the camera, but there are a few modifier keys
that you can use to control the behavior of the gesture:

- `Shift` allows you to pan the camera, i.e. move the camera in a straight line
  without rotating it.
- `Ctrl` or `⌘` allows you to move the camera backward and forward.

NOTE: Depending on your browser and platform, you might also be able to use
pinch gestures on your touchpad to move the camera backward and forward.

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

Next to the transformation mode buttons are two extra buttons. These control the
transformation space and transformation pivot.

You can think of the first button as controlling the orientation of your gizmo.
When a gizmo is oriented differently, it affects the direction of movement when
you move only a single axis.

There are two modes for this button:

- **Global** causes the gizmo to be aligned with the axis of your world. It will
  always be oriented the same, regardless of how your entity is oriented.
- **Local** causes the gizmo to have the same orientation as your entity.

The second button has no effect when only a single entity is selected, but when
you have multiple selected entities, it controls the position(s) of your
gizmo(s), and subsequently the pivot around which objects will rotate.

This button has three modes:

- **Center** places a single gizmo at the average location of all your selected
  entities.
- **Multiple** places an individual gizmo at every selected entity.
- **Last** places a single gizmo at the location of your last selected entity.
