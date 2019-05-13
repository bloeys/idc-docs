---
title: Adding a Command
position: 1.0
type: ""
description: How to add your own cmd to the IDC

content_markdown: |-
  The IDC allows you to add cmds so that they can be called from the terminal. Your cmds can either be public or private, and they can be static or in a static class.
  Each cmd is connected to its class instance, so non-static cmds will be called once per class instance, while static cmds will only be called once.

  Registered classes can be MonoBehaviours or normal C# classes. Normal C# classes can also be static.
  There is no unregister method as there is no need to unregister classes. The IDC will automatically detect when a class is 
  no longer used in the game and will remove it when the Unity Garbage Collector runs.

  Always remember to register your classes, otherwise your IDC cmds and variables will not be picked up.
  {: .info }

right_code_blocks:
  - title: Example 1
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

          //When the 'KillAllEnemies' method is called from the IDC, 
          //it will be run on each enemy, therefore killing all enemies
          [IDCCmd("KillAllEnemies")]
          void KillEnemy()
          {
              Destroy(gameObject);
          }
      }
  - title: Example 2
    language: csharp
    code_block: |-
      class Player : MonoBehaviour
      {
          public int maxHealth = 100;
          int health;

          void Start()
          {
              health = maxHealth;
              IDCUtils.IDC.AddClass(this);
          }

          [IDCCmd()]
          public void HealPlayer(int healAmount)
          {
              health += healAmount;

              if (health > maxHealth)
                  health = maxHealth;
          }
      }
---