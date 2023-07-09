# Preferences

Renda Studio has no single location where all preferences are stored. Instead,
you'll usually find the preference you're looking for inside the window related
to that preference. If a window has preferences available, it will show a button
in the top right corner with a gear icon. Clicking that will reveal a popover
containing all the preferences for that window.

NOTE: Windows can contain preferences that are not shown in this popover menu.
Though they are usually preferences that you wouldn't want to manually change
anyway. One such example is the camera position and rotation from the entity
editor.

## Preference Locations

The preferences popover contains a dropdown menu at the top that allows you to
choose the location where your changes will be stored. This allows you to only
change your preference for the current project for example.

These are locations you can choose from:

- **Global:** These preferences are stored in browser cookies. This causes the
  values to be shared across projects, windows, and workspaces.
- **Workspace:** These are stored in the current workspace. Switching to a
  different project will not cause the preference to change. But switching to a
  different workspace means the value will change in case it has been set.
- **Version Control:** Preferences are stored in a file in the current project.
  This file is tracked in git, meaning that if other users checkout the
  repository, they'll benefit (or suffer, depending on your decision!) from your
  changed value.
- **Project:** This is similar to 'Version Control' above, but this file has
  been `.gitignore`'d. So your changes will stay on your local device, and other
  users of the repository will not be surprised by your obscure configurations.
- **Window - Workspace:** This is similar to 'Workspace' except that the value
  is applied to the current window only. For example, this allows you to create
  two entity editors side by side. One where the grid is visible, and another
  where it isn't.
- **Window - Project:** Again, this is similar to 'Project' but stored inside
  the specific window where you are editing the value from.

The dropdown menu (and the above list) shows all the locations in order of
priority. So if a value has been modified inside the 'project' location, it will
take precedence over the value inside the 'global' location.

## The Default Location

The dropdown menu also has 'Default' as an option. This is not a location, but
it configures all preferences to use their preferred location. This means two
preferences can be visible next to each other, even though both store their
values at different locations.

Most of the time the default location for preferences is 'global', but sometimes
it makes more sense to store preferences somewhere else. One example is the
preference for controlling whether to allow your project to be remotely edited.
You likely only want to enable this for some projects, so by default, this
preference is stored in the 'project' location.

All preferences use sensible default locations. So you generally don't have to
worry about where it is stored.

## Where Are Preferences Stored?

Depending on which location you chose, you can inspect and modify preferences
manually. The main two files you'll want to look at are located at
`.renda/localPreferences.json` and `.renda/sharedPreferences.json` inside your
project folder. These contain the preferences for the 'Version Control',
'Project', and 'Window - Project' locations. `localPreferences.json` should be
`.gitignore`'d in order to not share these preferences with other team members.

Finally, the 'Workspace' and 'Window - Workspace' preferences are stored in your
browser, and can't easily be modified manually. Though if you wish to inspect
them, you can try looking for the 'workspaces' IndexedDB using your browser
inspector.
