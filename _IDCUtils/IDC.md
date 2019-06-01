---
title: IDC
position: 1.0
type: "var"
description: A variable that provides access to the running IDC instance

content_markdown: |-
  The **IDC** variable is a static variable in the IDCUtils class that has a reference to the IDC instance, and is the main way
  to use the IDC asset.
  
  Trying to use this variable at **Awake** when the scene first starts is *undefined* as the reference might not have been loaded yet.
  {: .warning}
---