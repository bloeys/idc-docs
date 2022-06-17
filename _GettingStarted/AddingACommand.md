---
title: Adding a Command
position: 1.1
type: ""
description: How to add your own cmd to the IDC

content_markdown: |-
  The IDC allows you to add any **method** as a command you can run from the terminal in-game. Methods you use as cmds can be public or private, static or not.

  Just keep in mind that if your cmd is not static then it will be called once per class instance, while static cmds will only be called once.
  So if you have 10 enemies each with a `Kill` method, then running the `Kill` cmd will call it 10 times, once on each enemy.

  Your new cmds will be added to the IDC when your class is registered (for example on `Start()`). Registered classes can be MonoBehaviours or normal C# classes, and normal C# classes can also be static.

  There is no need to unregister classes as The IDC will automatically detect when a class is 
  no longer used in the game and will remove it when the Garbage Collector runs.

  Always remember to register your classes, otherwise your IDC cmds and variables will not be picked up.
  {: .info }

  Make sure you are using the 'IDC' namespace `using IDC;`, otherwise IDC classes and methods won't be usable.
  {: .warning }

  Cmd names **must** contain only letters, numbers, and underscore.
  {: .warning }

right_code_blocks:
  - title: Example 1
    language: csharp
    code_block: |-
      using IDC;  //The IDC namespace is always required

      class Player : MonoBehaviour
      {
          int health;
          public int maxHealth = 100;

          void Start()
          {
              health = maxHealth;

              //Remember to register your classes!
              IDCUtils.IDC.AddClass(this);
          }

          //Since no cmd name is given, the IDC
          //will use the method name 'HealPlayer' as the cmd name
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
      using IDC;  //The IDC namespace is always required

      class Enemy : MonoBehaviour
      {
          public int health = 100;

          void Start()
          {
              //Each enemy created registers with the IDC
              IDCUtils.IDC.AddClass(this);
          }

          //When the 'KillAllEnemies' method is called from the IDC, 
          //it will run on each enemy, therefore killing all enemies
          [IDCCmd("KillAllEnemies")]
          void KillEnemy()
          {
              Destroy(gameObject);
          }
      }
  - title: Example 3
    language: csharp
    code_block: |-
      using IDC;  //The IDC namespace is always required

      class Enemy : MonoBehaviour
      {
          public int health = 100;

          void Start()
          {
              //Each enemy created registers with the IDC
              IDCUtils.IDC.AddClass(this);
          }

          /*Cmd name, description and access level. 
          Name and description are shown in the IDC autocomplete.
          The access level specifies where the cmd will be available.
          In this case, this cmd will only be available in the editor 
          and in dev builds.*/
          [IDCCmd("KillAllEnemies", "Destroy all enemy gameobjects", AccessLevel.EditorAndDevBuild)]
          void KillEnemy()
          {
              Destroy(gameObject);
          }
      }
  - title: Example 4
    language: csharp
    code_block: |-
      using IDC;  //The IDC namespace is always required

      class Player : MonoBehaviour
      {
          public int maxHealth = 100;
          int health;

          void Start()
          {
              health = maxHealth;
              IDCUtils.IDC.AddClass(this);
          }

          //Multiple IDC cmds can be made from
          //a single method
          [IDCCmd]
          [IDCCmd("SetPlayerHealth")]
          public void HealPlayer(int healAmount)
          {
              health += healAmount;

              if (health > maxHealth)
                  health = maxHealth;
          }
      }
---