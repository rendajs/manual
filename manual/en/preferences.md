# Preferences

Renda Studio has no single location where all preferences are stored. Instead, you'll usually find the preference you're
looking for inside the content window related to that preference. If a content window has preferences available, it will
show a button in the top right with a gear icon. Clicking that will reveal a popover containing all the preferences for
that content window.

NOTE: Content windows can contain preferences that are not shown in this popover menu. Though they are usually
preferences that you wouldn't want to manually change anyway. One such example is the camera position and rotation from
the entity editor.

## Preference Locations

The preferences popover contains a dropdown menu at the top that allows you to choose the location where your changes
will be stored. This allows you to only change your preference for the current project for example.

The locations you can choose from:

- **Global:** These preferences are stored in browser cookies. This causes the values to be shared across projects,
  content windows, and workspaces.
- **Workspace:** Preferences are stored in the current workspace. Switching to a different project will not cause the
  preference to change. But switching to a different workspace means the value will change to either that of the new
  workspace, or the global value depending on if the new workspace has a value configured.
- **Version Control:** Preferences are stored in a file in the current project. This file is tracked in git, meaning
  that if other users checkout the repository, they'll benefit (or suffer, depending on your decision!) from your
  changed value.
- **Project:** This is similar to 'Version Control' above, but this file has been `.gitignore`'d. So your changes will
  stay on your local device, and other users of the repository will not be surprised by your obscure configurations.
- **Window - Workspace:** This is similar to 'Workspace' except that the value is applied to the current content window
  only. For example, this allows you to create two entity editors side by side. One where the grid is visible, and
  another where it isn't.
- **Window - Project:** Again, this is similar to 'Project' but stored inside the specific content window where you are
  editing the value from.

The dropdown menu (and the above list) shows all the locations in order of priority. So if a value has been modified
inside the 'project' location, it will take precedence over the value inside the 'global' location.

## The Default Location

The dropdown menu also has 'Default' as an option. This is not a location, but when 'Default' is selected, all
preferences will use their default location. This means two preferences can be visible next to each other, even though
both store their values at different locations.

Most of the time the default location for preferences is 'global', but sometimes it makes more sense to store
preferences somewhere else by default. All preferences use sensible default locations. So you generally don't have to
worry about where it is stored.
