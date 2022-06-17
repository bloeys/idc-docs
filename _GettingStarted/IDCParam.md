---
title: IDCParam Attribute
position: 1.3
type: ""
description: Adding custom suggestions for a cmd parameter

content_markdown: |-
  You can use the `IDCParam` attribute on top of IDC method parameters to show additional suggestions in the terminal.

  ![idc-param](idc-param.png)

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      using UnityEngine;
      using IDC;

      public class BossAI : MonoBehaviour
      {
          [IDCVar]
          int aggressivenessLvl = 1;

          void Start()
          {
              IDCUtils.IDC.AddClass(this);
          }

          [IDCCmd]
          void SetAggroLvl([IDCParam("1", "2", "3")] int lvl)
          {
              aggressivenessLvl = lvl;
          }
      }
---