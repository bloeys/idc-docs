---
title: RegisterParamSuggestionsFunc
position: 1.4
type: ""
description: Takes a function that will be called when suggestions are needed for a parameter

parameters:
  - name: string cmdName
    content: The name of the command that contains the wanted parameter
  - name: string paramName
    content: The name of the parameter
  - name: Func<string[]> func
    content: The function to be called when the IDC needs suggestions

content_markdown: |-
    Similar to **UpdateParamSuggestions**, but instead of providing suggestions once it provides a function to the IDC that 
    when called returns the array of suggestions.

    This is useful when you want to provide dynamic suggestions that change depending on the conditions of your game.

    The passed function is only called when the user is being shown the suggestions of the parameter targeted by this method.
    {: .info}

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      //Show the following values as suggestions for the 'lineSpacing' parameter of the 'SetLogAreaLineSpacing' command
      string[] mySuggestions = new string[] { "1", "1.2", "1.4", "1.6" };
      IDCUtils.IDC.UpdateParamSuggestions("SetLogAreaLineSpacing", "lineSpacing", mySuggestions);
---