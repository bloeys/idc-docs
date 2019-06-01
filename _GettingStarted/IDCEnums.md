---
title: IDC Enums
position: 1.2
type: ""
description: IDCCmdsEnum and IDCVarsEnum

content_markdown: |-
  The IDC can generate two enums, 'IDCCmdsEnum', which contains the names of all your IDC cmds,
  and 'IDCVarsEnum', which contains the names of IDC variables and their classes.

  They are not strictly required, but can be used by other methods. One example is that the
  'RunCmdFromString' method uses the IDCCmdsEnum.

  When you add/remove an IDC cmd/var you need to regenerate the enums. You can do this by
  simply clicking on the 'Update IDC Enums' in the IDC Prefab.
  {: .warning }

---