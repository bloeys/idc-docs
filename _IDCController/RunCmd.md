---
title: RunCmd
position: 1.2
type: ""
description: Runs an IDC command from a passed string

parameters:
  - name: IDCCmdsEnum <em>cmd</em>
    content: The command to be executed
  - name: string <em>args</em>
    content: The args passed to the cmd 

content_markdown: |-
  The args string **must** be in the same format as commands entered in the IDC UI while in-game.

right_code_blocks:
  - title: Example 1
    language: csharp
    code_block: |-
      IDCUtils.IDC.RunCmd(IDCCmdsEnum.SetCmdColor, " - red");
  - title: Example 2
    language: csharp
    code_block: |-
      //Sets the color to white by using the constructor of the Color struct
      IDCUtils.IDC.RunCmd(IDCCmdsEnum.SetCmdColor, " - (1, 1, 1, 1)");
---