---
title: SetStringSize
position: 1.4
type: ""
description: Surrounds the string with the 'size' rich text tag

parameters:
  - name: string <em>s</em>
    content: The string to surround with the rich text tag
  - name: float <em>newSize</em>
    content: The new size of the passed string

content_markdown: |-
  Returns the original string but surrounded with the **size** tag set to the passed size.

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      string myLargeString = IDCUtils.SetStringSize("Hello IDC!", 25.5f);

---