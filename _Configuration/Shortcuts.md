---
title: Shortcut Profiles
position: 1.1
type: ""
description: Assigning shortcuts to your cmds

content_markdown: |-
  Shortcut profiles are very similar to settings, they are simply scriptable objects
  that contain shortcut assignments. Again, this allows you to have different
  sets of shortcuts that you can simply swapout.

  Shortcut profiles can be changed by assigning them directly to the IDC prefab or
  by using the 'SetIDCShortcutProfile' cmd.

  By default, shortcut profiles are stored in 'Ingame Developer Console/Shortcut Profiles'.
  New profiles can be created by clicking the 'Create New IDC Shortcut Profile' button on
  the IDC prefab.

  In the image below, you can see an example of a single cmd attached to the 'LeftCtrl + L' 
  shortcut.

  Multiple cmds can be attached to one shortcut.
  {: .info }

  Shortcut cmds **must** take **zero** arguments.
  {: .warning }

  ![idc-shortcuts](idc-shortcut.png)
---