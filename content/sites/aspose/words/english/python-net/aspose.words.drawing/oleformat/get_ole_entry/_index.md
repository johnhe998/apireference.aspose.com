﻿---
title: OleFormat.get_ole_entry method
linktitle: get_ole_entry method
articleTitle: get_ole_entry method
second_title: Aspose.Words for Python
description: "OleFormat.get_ole_entry method. Gets OLE object data entry."
type: docs
weight: 140
url: /python-net/aspose.words.drawing/oleformat/get_ole_entry/
---

## get_ole_entry(ole_entry_name) {#str}

Gets OLE object data entry.


```python
def get_ole_entry(self, ole_entry_name: str):
    ...
```

| Parameter | Type | Description |
| --- | --- | --- |
| ole_entry_name | str |  |

### Returns

An OLE data stream or ``None``.


### Examples

Shows how to insert linked and unlinked OLE objects.

```python
doc = aw.Document()
builder = aw.DocumentBuilder(doc)

# Embed a Microsoft Visio drawing into the document as an OLE object.
builder.insert_ole_object(IMAGE_DIR + "Microsoft Visio drawing.vsd", "Package", False, False, None)

# Insert a link to the file in the local file system and display it as an icon.
builder.insert_ole_object(IMAGE_DIR + "Microsoft Visio drawing.vsd", "Package", True, True, None)

# Inserting OLE objects creates shapes that store these objects.
shapes = [node.as_shape() for node in doc.get_child_nodes(aw.NodeType.SHAPE, True)]

self.assertEqual(2, len(shapes))
self.assertEqual(2, len([shape for shape in shapes if shape.shape_type == aw.drawing.ShapeType.OLE_OBJECT]))

# If a shape contains an OLE object, it will have a valid "ole_format" property,
# which we can use to verify some aspects of the shape.
ole_format = shapes[0].ole_format

self.assertEqual(False, ole_format.is_link)
self.assertEqual(False, ole_format.ole_icon)

ole_format = shapes[1].ole_format

self.assertEqual(True, ole_format.is_link)
self.assertEqual(True, ole_format.ole_icon)

self.assertTrue(ole_format.source_full_name.endswith("Images/Microsoft Visio drawing.vsd"))
self.assertEqual("", ole_format.source_item)

self.assertEqual("Microsoft Visio drawing.vsd", ole_format.icon_caption)

doc.save(ARTIFACTS_DIR + "Shape.ole_links.docx")

# If the object contains OLE data, we can access it using a stream.
stream = ole_format.get_ole_entry("\u0001CompObj")
stream.seek(0)
ole_entry_bytes = stream.read()
self.assertEqual(76, len(ole_entry_bytes))
```

### See Also

* module [aspose.words.drawing](../../)
* class [OleFormat](../)

