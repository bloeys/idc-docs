---
title: Adding a Command
position: 1.0
type: ""
description: How to add your own cmd to the IDC

# parameters:
#   - name: string <em>s</em>
#     content: The string to surround with the rich text tag
#   - name: Color <em>c</em>
#     content: The color to use for the passed string

content_markdown: |-
  The IDC allows you to add cmds so that they can be called from the terminal. Your cmds can either be public or private, and they can be static or in a static class.
  Each cmd is connected to its class instance, so non-static cmds will be called once per class instance, while static cmds will only be called once.

right_code_blocks:
  - title: Static Cmd
    language: csharp
    code_block: |-
      class Enemy : MonoBehaviour
      {
          public int health = 100;

          void Start()
          {
              //Each enemy created registers with the IDC
              IDCUtils.IDC.AddClass(this);
          }

          //When the method is called from the IDC, it will be run
          //on each enemy, therefore killing all enemies
          [IDCCmd]
          void KillEnemy()
          {
              Destroy(gameObject);
          }
      }
---