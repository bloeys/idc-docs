---
title: AddClass
position: 1.0
type: ""
description: Registers the class instance with the IDC

parameters:
  - name: object classInstance
    content: The class instance to register

content_markdown: |-
  Adding a class registers all its commands and variables with the IDC.

  Adding a class in the **Awake** method of a GameObject that is loaded at scene start might fail. If your object is available from scene start then 
  you should add it in the **Start** method.
  {: .warning}

  The class will automatically be removed from the IDC when it's garbage collected (e.g. When its GameObject is destroyed)
  {: .info }

left_code_blocks:
  - title: Example
    language: C#
    code_block: |-
      void Start()
      {
        IDCUtils.IDC.AddClass(this);  //Adds the current class to the IDC
      }

right_code_blocks:
  - code_block:
    title:
    language:
---