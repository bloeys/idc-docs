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
    Similar to **SetParamSuggestions**, but instead of hard-coding suggestions you provide a function to the IDC that
    gets called automatically by the IDC when it needs suggestions for a param. This function returns an array of suggestions that get shown along with the automatic ones.

    This is useful when you want to provide dynamic suggestions that change depending on the conditions of your game.

    The passed function is only called when the user is being shown the suggestions of the parameter targeted by this method.
    {: .info}

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      void Start()
      {
        IDCUtils.IDC.SetParamSuggestionsFunc(
          IDCCmdsEnum.SetLogAreaLineSpacing, 
          "lineSpacing", 
          GetLogLineSpacingSugg);
      }

      string[] GetLogLineSpacingSugg()
      {
        //Return a random linespacing between 1-2 as a suggestion
        string lineSpacing = Random.Range(1f, 2f).ToString();
        return new string[] { lineSpacing };
      }
---