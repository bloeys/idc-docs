---
title: UpdateParamSuggestions
position: 1.3
type: ""
description: Sets the user suggestions for a command parameter

parameters:
  - name: string cmdName
    content: The name of the command that contains the wanted parameter
  - name: string paramName
    content: The name of the parameter
  - name: string[] newSugg
    content: An array of suggestions to show for this parameter when using the UI

content_markdown: |-
    User provided suggestions are shown before IDC provided ones.
    
    Suggestions also support Rich Text, and so properties like color can be controlled if wanted. The full list of supported
    tags are shown [here](https://docs.unity3d.com/Manual/StyledText.html).

    User provided suggestions override suggestions set by the **IDCParam** attribute.
    {: .warning}

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      //Show the following values as suggestions for the 'lineSpacing' parameter of the 'SetLogAreaLineSpacing' command
      string[] mySuggestions = new string[] { "1", "1.2", "1.4", "1.6" };
      IDCUtils.IDC.UpdateParamSuggestions("SetLogAreaLineSpacing", "lineSpacing", mySuggestions);
---