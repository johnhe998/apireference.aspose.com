﻿---
title: FindReplaceOptions.ignore_field_codes property
linktitle: ignore_field_codes property
articleTitle: ignore_field_codes property
second_title: Aspose.Words for Python
description: "FindReplaceOptions.ignore_field_codes property. Gets or sets a boolean value indicating either to ignore text inside field codes"
type: docs
weight: 70
url: /python-net/aspose.words.replacing/findreplaceoptions/ignore_field_codes/
---

## FindReplaceOptions.ignore_field_codes property

Gets or sets a boolean value indicating either to ignore text inside field codes.
The default value is ``False``.


This option affects only field codes (it does not ignore nodes between
[NodeType.FIELD_SEPARATOR](../../../aspose.words/nodetype/#FIELD_SEPARATOR) and [NodeType.FIELD_END](../../../aspose.words/nodetype/#FIELD_END)).

To ignore whole field, please use corresponding option [FindReplaceOptions.ignore_fields](../ignore_fields/).




### Examples

Shows how to ignore text inside field codes.

```python
doc = aw.Document()
builder = aw.DocumentBuilder(doc)

builder.insert_field("INCLUDETEXT", "Test IT!")

options = aw.replacing.FindReplaceOptions()
options.ignore_field_codes = ignore_field_codes

# Replace 'T' in document ignoring text inside field code or not.
doc.range.replace_regex("T", "*", options)
print(doc.get_text())

if ignore_field_codes:
    self.assertEqual("\u0013INCLUDETEXT\u0014*est I*!\u0015", doc.get_text().strip())
else:
    self.assertEqual("\u0013INCLUDE*EX*\u0014*est I*!\u0015", doc.get_text().strip())
```

### See Also

* module [aspose.words.replacing](../../)
* class [FindReplaceOptions](../)

