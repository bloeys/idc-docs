---
title: AddAssetToSuggest
position: 1.5
type: ""
description: Shows autocomplete for project assets

parameters:
  - name: Type <em>asset</em>
    content: Type of unity asset to autocomplete for

content_markdown: |-
    The IDC will show autocomplete for parameters with types matching the passed
    asset type. The suggestions come from the assets of that type found in the
    project window of Unity.

    For example, you can use this cmd to make the IDC show you the suggestions
    for materials found in your project. 
    
    When this is cmd called, the IDC will get all assets of the wanted type and
    cache them so that showing suggestions is faster. 

    In the example image, you can see
    how two different materials, 'RedMat' and 'MyBlueMat' are suggested
    for the material parameter requested by a custom cmd.
    
    Note that this cmd *could* be a bit slow if your project has a huge,
    so it is recommended to call it in 'Start' when your scene first loads.
    {: .info}

    ![idc-settings](res/idc-asset-sugg.png)

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      IDCUtils.IDC.AddAssetToSuggest(typeof(Material));
---