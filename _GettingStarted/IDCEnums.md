---
title: IDC Enums
position: 1.4
type: ""
description: IDCCmdsEnum and IDCVarsEnum

content_markdown: |-
  The IDC generates two enums, 'IDCCmdsEnum', which contains the names of all your IDC cmds,
  and 'IDCVarsEnum', which contains the names of IDC variables and their classes.

  They are used to show you better suggestions and can be used to run IDC cmds from code.
  For example you can run an IDC cmd through the `IDCUtils.IDC.RunCmd` method, which requires the IDCCmdsEnum.

  If you disabled auto-regenerate in the settings then you should click the 'Update IDC Enums' button in the IDC prefab whenever you add/remove an IDC cmd or var.
  {: .warning }

---