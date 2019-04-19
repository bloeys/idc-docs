---
title: ExecuteCmdFromString
position: 1.2
type: ""
description: Runs an IDC command from a passed string

parameters:
  - name: string <em>cmd</em>
    content: The command to be executed and its arguments

content_markdown: |-
  The string **must** be in the same format as commands entered in the IDC UI while in-game.

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      IDCUtils.IDC.ExecuteCmdFromString("SetCmdColor - red");
  - title: Example 2
    language: csharp
    code_block: |-
      //Sets the color to white by using the constructor of the Color struct
      IDCUtils.IDC.ExecuteCmdFromString("SetCmdColor - [1, 1, 1, 1]");
---