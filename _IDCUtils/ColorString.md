---
title: ColorString
position: 1.0
type: ""
description: Surrounds the string with the rich text tag of the wanted color

parameters:
  - name: string <em>s</em>
    content: The string to surround with the rich text tag
  - name: Color <em>c</em>
    content: The color to use for the passed string

content_markdown: |-
  Converts the passed RGBA color to the equivalent Hexadecimal representation and uses that result in the rich text tag.
  Returns the original string but surrounded with the appropriate color tag.

right_code_blocks:
  - title: Example
    language: csharp
    code_block: |-
      string myColoredString = IDCUtils.ColorString("Hello World!", Color.green);
---