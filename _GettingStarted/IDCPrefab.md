---
title: The Ingame Developer Console
position: 0.9
type: ""
description: Introduction

content_markdown: |-
  The Ingame Developer Console (IDC) is a super powerful and easy to use ingame console/terminal, which allows you to speed up your game's development, help with debugging, and even add cheats to your game!.

  After registering your C# classes with the IDC, you can turn methods into new console commands (called 'cmds') with full autocomplete and type checking using a single line of code!
  
  Your cmds can have any number of parameters and any parameter types, including classes and structs.
  On top of this, the IDC allows you to track and even change the values of variables through the 'Vars Window'.

---
title: The Ingame Developer Console Prefab
position: 1.0
type: ""
description: Adding the IDC to your scene

content_markdown: |-
  To start simply add the '**IDCCanvas**' prefab to your scene. You can find this prefab in the 'Assets/Ingame Developer Console/Prefabs' folder.
  
  When your game is running you can toggle the console window by using the Backquote/Backtick key (**`**).

  ![idc-console](res/idc-console.png)

  The IDC will not work if you don't add the IDC prefab to your scene.
  {: .warning }
