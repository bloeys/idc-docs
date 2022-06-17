---
title: IDCParam Attribute
position: 1.3
type: ""
description: Adding custom suggestions for a cmd parameter

content_markdown: |-
  You can use the `IDCParam` attribute on top of IDC method parameters to show additional suggestions in the terminal.

  ![idc-param](res/idc-param.png)

right_code_blocks:
  - title: Example 1
    language: csharp
    code_block: |-
      using UnityEngine;
      using IDC;

      public class NPC : MonoBehaviour
      {
          string NPCType;

          void Start()
          {
              IDCUtils.IDC.AddClass(this);
          }

          //These three options will be shown as suggestions
          [IDCCmd]
          void SetNPCType([IDCParam("Friendly", "Passive", "Enemy")] string npcType)
          {
              NPCType = npcType;
          }
      }

  - title: Example 2
    language: csharp
    code_block: |-
      using UnityEngine;
      using IDC;

      public class TreasureChest : MonoBehaviour
      {
          void Start()
          {
              IDCUtils.IDC.AddClass(this);
          }

          //This will show the numbers 1, 2, 3, 4, and 5 as suggestions.
          //A different increment and floats can be used as well.
          [IDCCmd]
          void GetItemOfLvl([IDCParam(1, 5)] int lvl)
          {
              //Magic goes here
          }
      }
---