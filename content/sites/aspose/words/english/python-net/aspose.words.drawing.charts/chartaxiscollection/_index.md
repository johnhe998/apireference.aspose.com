﻿---
title: ChartAxisCollection class
linktitle: ChartAxisCollection class
articleTitle: ChartAxisCollection class
second_title: Aspose.Words for Python
description: "aspose.words.drawing.charts.ChartAxisCollection class. Represents a collection of chart axes."
type: docs
weight: 140
url: /python-net/aspose.words.drawing.charts/chartaxiscollection/
---

## ChartAxisCollection class

Represents a collection of chart axes.


### Indexers

| Name | Description |
| --- | --- |
| [``__getitem__(index)``](./__getitem__/#int) | Gets the axis at the specified index. |

### Properties

| Name | Description |
| --- | --- |
| [count](./count/) | Gets the number of axes in this collection. |

### Examples

Shows how to work with axes collection.

```python
doc = aw.Document()
builder = aw.DocumentBuilder(doc)

shape = builder.insert_chart(awdc.ChartType.COLUMN, 500, 300)
chart = shape.chart

# Hide the major grid lines on the primary and secondary Y axes.
for axis in chart.axes:
    if axis.type == awdc.ChartAxisType.VALUE:
        axis.has_major_gridlines = False

doc.save(ARTIFACTS_DIR + "Charts.AxisCollection.docx")
```

### See Also

* module [aspose.words.drawing.charts](../)

