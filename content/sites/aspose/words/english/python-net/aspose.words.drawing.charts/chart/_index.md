﻿﻿---
title: Chart class
linktitle: Chart class
articleTitle: Chart class
second_title: Aspose.Words for Python
description: "aspose.words.drawing.charts.Chart class. Provides access to the chart shape properties"
type: docs
weight: 120
url: /python-net/aspose.words.drawing.charts/chart/
---

## Chart class

Provides access to the chart shape properties.
To learn more, visit the [Working with Charts](https://docs.aspose.com/words/python-net/working-with-charts/) documentation article.




### Properties

| Name | Description |
| --- | --- |
| [axes](./axes/) | Gets a collection of all axes of this chart. |
| [axis_x](./axis_x/) | Provides access to properties of the X axis of the chart. |
| [axis_y](./axis_y/) | Provides access to properties of the Y axis of the chart. |
| [axis_z](./axis_z/) | Provides access to properties of the Z axis of the chart. |
| [legend](./legend/) | Provides access to the chart legend properties. |
| [series](./series/) | Provides access to series collection. |
| [source_full_name](./source_full_name/) | Gets the path and name of an xls/xlsx file this chart is linked to. |
| [title](./title/) | Provides access to the chart title properties. |

### Examples

Shows how to insert a chart and set a title.

```python
doc = aw.Document()
builder = aw.DocumentBuilder(doc)

# Insert a chart shape with a document builder and get its chart.
chart_shape = builder.insert_chart(aw.drawing.charts.ChartType.BAR, 400, 300)
chart = chart_shape.chart

# Use the "title" property to give our chart a title, which appears at the top center of the chart area.
title = chart.title
title.text = "My Chart"

# Set the "show" property to "True" to make the title visible.
title.show = True

# Set the "overlay" property to "True" Give other chart elements more room by allowing them to overlap the title
title.overlay = True

doc.save(ARTIFACTS_DIR + "Charts.chart_title.docx")
```

### See Also

* module [aspose.words.drawing.charts](../)

