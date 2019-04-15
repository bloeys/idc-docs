---
title: void GetSomething(string asd)
position: 1
type: ""
description: Get Book
parameters:
  - name:
    content:
content_markdown: |-
  Returns a specific book from your collection
left_code_blocks:
  - code_block: |-
      GetSomething("ASD");
    title: jQuery
    language: csharp

right_code_blocks:
  - code_block: |2-
      {
        "id": 3,
        "title": "The Book Thief",
        "score": 4.3,
        "dateAdded": "5/1/2015"
      }
    title: Response
    language: json
  - code_block: |2-
      {
        "error": true,
        "message": "Book doesn't exist"
      }
    title: Error
    language: json
---