# Properties Window

The properties window is pretty dynamic in what it can show. It can show all
sorts of things depending on your current selection. The main types of selection
you'll be working with, are assets and entities.

## Working With Selected Entities

When you have selected an entity, the properties window will show you controls
for manipulating that entity. Specifically its location, or any of its
components.

The top section of this window is dedicated to changing the location of the
entity. Here you can adjust the values for the position, rotation, and scale.

NOTE: The **Editing Mode** setting is an old artifact that is not functional at
the moment.

The bottom section of the window allows you to modify the components of a
selected entity. Each component has its own interface depending on what type of
component it is, so we won't talk too much about individual components here.

To add a new component, you can use the **+** button.

To remove a component, right-click the name of that component and choose
**Remove**.

## Working With Selected Assets

Assets from the project window can also be selected. The interface that is shown
in that case is highly dependent on the type of asset that was selected. Some
assets don't even show any interface at all.

Generally speaking, there are two types of interfaces for selected assets:

- Interfaces that directly map to the content in the asset. Many assets with the
  `.json` extension behave like this, it is very easy to inspect these files in
  a text editor. Examples include vertex state, render output config, and
  clustered lights config assets.
- Assets that don't directly map to the content on disk. These assets have a
  custom interface, either because they are too complex to show in an interface,
  like mesh assets, or because they require a custom interface to make them
  easier to work with, like task assets. These types of assets can often still
  easily be inspected within a text editor. But the interface shown in Renda
  Studio might differ a bit from how it's structured inside the JSON file.

## Multiple Selections at Once

Multiple windows in Renda Studio can have their own selection. For instance, the
outliner might have selected one or more entities, but the project window may
have selected one or more assets as well. The properties window can only show
one type of selection at a time though. So it will use the selection from the
window you used last.

Your selections will still be maintained, however. So if you want, you can
toggle back and forth between the selection of the outliner and project window
simply by clicking them. This is especially useful when you have multiple items
selected in a window. You don't have to select each item again, just make sure
you click an empty area of a window to focus it.

NOTE: Editing multiple assets or entities at once is
[currently not supported](https://github.com/rendajs/Renda/issues/387), even if
those assets all have the same type. Generally speaking, only the first selected
item will be modified when you make changes.
