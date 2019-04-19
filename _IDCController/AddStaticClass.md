---
title: AddStaticClass
position: 1.1
type: ""
description: Registers a static class with the IDC

parameters:
  - name: Type classType
    content: The type of the class to register

content_markdown: |-
  Adding a class registers all of its commands and variables with the IDC.

  Adding a class in the **Awake** method of a GameObject that is loaded at scene start might fail. If your object is available from scene start then 
  you should add it in the **Start** method.
  {: .warning}

left_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      void Start()
      {
        IDCUtils.IDC.AddStaticClass(typeof(MyStaticClass));
      }
---