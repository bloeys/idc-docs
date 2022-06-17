---
title: Adding a Variable
position: 1.2
type: ""
description: How to track your variables with the IDC

content_markdown: |-
  The IDC allows you to both track your variables and to edit their values through the 'Vars Window'.
  To open the vars window run the `ShowVarsWindow` IDC cmd.

  The window shows you a list of game objects, and under each object the registered classes that are
  attached to that game object, and under each class a list of registered variables.
  
  ![vars-window](res/idc-vars-window.png)

  The vars window can be moved by dragging it, and resized from the
  bottom-right corner of the window.
  {: .info }

  Just like cmds, variable names **must** contain only letters, numbers, and underscore.
  {: .warning }

  You can also change the value of an IDC Var by using the `SetVarValue` cmd. This cmd takes the
  name of the variable and its new value, along with the game object and class to change the variable on.

  ![set-var-value-1](res/idc-set-var-value-1.png)

  After running the previous cmd the health on 'Enemy Copy 2' will become 9999. 

  ![set-var-value-1](res/idc-set-var-value-2.png)

  If you don't select a game object and a class then all instances of variable are changed.

  The class index is the number after the class name. In the above image, '(Enemy:0)' means the class called 'Enemy' and an index of zero.
  {: .info}

  If your class is used on multiple game objects, you must use the index on the game object you are choosing
  {: .warning}

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
          //Give custom names to these variables
          [IDCVar("Enemy_speed")]
          public float speed = 2;

          [IDCVar("Enemy_Health")]
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
  - title: Example 3
    language: csharp
    code_block: |-
      using IDC;

      class MiniBoss : MonoBehaviour
      {
          //Again some custom names to these variables
          [IDCVar("Boss_AI")]
          int aggressivenessLvl = 3;

          [IDCVar("Boss_Speed")]
          float speed = 5.5f;

          [IDCVar("Boss_health")]
          int health = 999;

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
