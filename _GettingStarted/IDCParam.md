---
title: IDCParam Attribute
position: 1.3
type: ""
description: Adding custom suggestions for a cmd parameter

content_markdown: |-
  The IDCParam attribute can be added to parameters of an IDC cmd.

  It is used to give some suggestions that will be shown in the
  console window when that parameter is being used.

  ![vars-window](idc-param.png)

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