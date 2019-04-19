---
title: AddClass
position: 1.0
type: ""
description: Registers the class instance with the IDC

parameters:
  - name: object <em>classInstance</em>
    content: The class instance to register

content_markdown: |-
  Adding a class registers all of its commands and variables with the IDC.

  The class will automatically be removed from the IDC when it's garbage collected (e.g. When its GameObject is destroyed)
  {: .info }

  Adding a class in the **Awake** method of a GameObject that is loaded at scene start might fail. If your object is available from scene start then 
  you should add it in the **Start** method.
  {: .warning}

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      void Start()
      {
        IDCUtils.IDC.AddClass(this);  //Adds the current class to the IDC
      }
---