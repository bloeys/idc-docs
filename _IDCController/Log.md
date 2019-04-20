---
title: Log
position: 1.5
type: ""
description: Logs the passed message to the IDC console

parameters:
  - name: string <em>msg</em>
    content: The message to log to the console

content_markdown: |-
  Logs a string to the IDC console directly and does not show on the Unity console. Supports Rich Text.

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      IDCUtils.IDC.Log("My log message");
  - title: Example 2
    language: csharp
    code_block: |-
      IDCUtils.IDC.Log("My red log message", Color.red);
  - title: Example 3
    language: csharp
    code_block: |-
      IDCUtils.IDC.Log("My default colored warning", LogType.Warning);
  - title: Example 4
    language: csharp
    code_block: |-
      IDCUtils.IDC.Log("My custom colored warning", Color.blue, LogType.Warning);
---