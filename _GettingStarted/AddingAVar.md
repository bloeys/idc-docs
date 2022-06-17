---
title: Adding a Variable
position: 1.2
type: ""
description: How to track your variables with the IDC

content_markdown: |-
  The IDC allows you to both track your variables and to edit their values. All IDC vars 
  are shown in the 'Vars Window', where it is shown which game object and class each variable belongs to.

  To open the vars window, simply run the `ShowVarsWindow` IDC cmd. This also forces
  the window to update.
  
  ![vars-window](idc-vars-window.png)

  The vars window can be moved by dragging it, and resized from the
  bottom-right corner of the window.
  {: .info }

right_code_blocks:
  - title: Example 1
    language: csharp
    code_block: |-
      using IDC;

      class Player : MonoBehaviour
      {
          public int maxHealth = 100;

          //Just like IDCCmd, this will use the
          //variable's name if no name is given
          [IDCVar]
          int health;

          void Start()
          {
              health = maxHealth;

              //Always remember to register
              IDCUtils.IDC.AddClass(this);
          }

          [IDCCmd]
          public void HealPlayer(int healAmount)
          {
              health += healAmount;

              if (health > maxHealth)
                  health = maxHealth;
          }
      }
  - title: Example 2
    language: csharp
    code_block: |-
      using IDC;

      class Enemy : MonoBehaviour
      {
          [IDCVar("enemyHealth")]
          public int health = 100;

          void Start()
          {
              IDCUtils.IDC.AddClass(this);
          }

          [IDCCmd("KillAllEnemies")]
          void KillEnemy()
          {
              Destroy(gameObject);
          }
      }
---