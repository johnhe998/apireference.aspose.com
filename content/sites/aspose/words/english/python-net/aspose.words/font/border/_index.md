﻿---
title: Font.border property
linktitle: border property
articleTitle: border property
second_title: Aspose.Words for Python
description: "Font.border property. Returns a [Border](../../border/) object that specifies border for the font."
type: docs
weight: 60
url: /python-net/aspose.words/font/border/
---

## Font.border property

Returns a [Border](../../border/) object that specifies border for the font.



### Examples

Shows how to insert a string surrounded by a border into a document.

```python
doc = aw.Document()
builder = aw.DocumentBuilder(doc)

builder.font.border.color = drawing.Color.green
builder.font.border.line_width = 2.5
builder.font.border.line_style = aw.LineStyle.DASH_DOT_STROKER

builder.write("Text surrounded by green border.")

doc.save(ARTIFACTS_DIR + "Border.font_border.docx")
```

### See Also

* module [aspose.words](../../)
* class [Font](../)

