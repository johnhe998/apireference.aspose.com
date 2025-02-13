﻿---
title: OleControl.name property
linktitle: name property
articleTitle: name property
second_title: Aspose.Words for Python
description: "OleControl.name property. Gets or sets name of the ActiveX control."
type: docs
weight: 20
url: /python-net/aspose.words.drawing.ole/olecontrol/name/
---

## OleControl.name property

Gets or sets name of the ActiveX control.


### Examples

Shows how to verify the properties of an ActiveX control.

```python
doc = aw.Document(MY_DIR + "ActiveX controls.docx")

shape = doc.get_child(aw.NodeType.SHAPE, 0, True).as_shape()
ole_control = shape.ole_format.ole_control

self.assertEqual("CheckBox1", ole_control.name)

if ole_control.is_forms2_ole_control:

    check_box = ole_control.as_forms2_ole_control()
    self.assertEqual("Первый", check_box.caption)
    self.assertEqual("0", check_box.value)
    self.assertEqual(True, check_box.enabled)
    self.assertEqual(aw.drawing.ole.Forms2OleControlType.CHECK_BOX, check_box.type)
    self.assertIsNone(check_box.child_nodes)
    self.assertEqual("", check_box.group_name)

    # Note, that you can't set GroupName for a Frame.
    check_box.group_name = "Aspose group name"
```

### See Also

* module [aspose.words.drawing.ole](../../)
* class [OleControl](../)

