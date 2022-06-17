---
title: SetParamSuggestions
position: 1.3
type: ""
description: Sets the user suggestions for a command parameter

parameters:
  - name: IDCCmdsEnum <em>cmd</em>
    content: The name of the command that contains the wanted parameter
  - name: string <em>paramName</em>
    content: The name of the parameter
  - name: string[] <em>newSugg</em>
    content: An array of suggestions to show for this parameter when using the UI

content_markdown: |-
    This is essentially a runtime version of the `IDCParam` attribute, which allows you to override the suggestions of `IDCParam`.
    
    Just as with the attribute, suggestions support Rich Text and the list of supported tags can be found [here](https://docs.unity3d.com/Manual/StyledText.html).

    User provided suggestions get shown before IDC provided ones
    {: .info}

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      //Show the following values as suggestions for the 'lineSpacing' parameter of the 'SetLogAreaLineSpacing' command
      string[] mySuggestions = new string[] { "1", "1.2", "1.4", "1.6" };
      
      IDCUtils.IDC.SetParamSuggestions(
        IDCCmdsEnum.SetLogAreaLineSpacing, 
        "lineSpacing", mySuggestions);
---