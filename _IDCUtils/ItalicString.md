---
title: ItalicString
position: 1.3
type: ""
description: Surrounds the string with the 'i' rich text tag

parameters:
  - name: string <em>s</em>
    content: The string to surround with the rich text tag

content_markdown: |-
  Returns the original string but surrounded with the **i** tag.

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      string myItalicString = IDCUtils.ItalicString("Hello World");
---