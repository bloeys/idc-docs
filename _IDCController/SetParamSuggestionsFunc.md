---
title: SetParamSuggestionsFunc
position: 1.4
type: ""
description: Takes a function that will be called when suggestions are needed for a parameter

parameters:
  - name: IDCCmdsEnum <em>cmd</em>
    content: The name of the command that contains the wanted parameter
  - name: string <em>paramName</em>
    content: The name of the parameter
  - name: Func&lt;string[]&gt; <em>func</em>
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
      string[] GetLogLineSpacingSugg()
      {
        //Return a random linespacing between 1-2 as a suggestion
        string lineSpacing = Random.Range(1f, 2f).ToString();
        return new string[] { lineSpacing };
      }

      void Start()
      {
        IDCUtils.IDC.SetParamSuggestionsFunc(
          IDCCmdsEnum.SetLogAreaLineSpacing, 
          "lineSpacing", GetLogLineSpacingSugg);
      }
---