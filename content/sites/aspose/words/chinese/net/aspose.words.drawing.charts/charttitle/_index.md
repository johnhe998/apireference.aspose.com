---
title: Class ChartTitle
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.ChartTitle 班级. 提供对图表标题属性的访问
type: docs
weight: 750
url: /zh/net/aspose.words.drawing.charts/charttitle/
---
## ChartTitle class

提供对图表标题属性的访问。

```csharp
public class ChartTitle
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Overlay](../../aspose.words.drawing.charts/charttitle/overlay/) { get; set; } | 确定是否允许其他图表元素重叠 title. 默认情况下覆盖为 false。 |
| [Show](../../aspose.words.drawing.charts/charttitle/show/) { get; set; } | 确定是否应为此图表显示标题。 默认值为 true。 |
| [Text](../../aspose.words.drawing.charts/charttitle/text/) { get; set; } | 获取或设置图表标题的文本。 如果指定null或空值，将显示自动生成的标题。 |

### 例子

显示如何插入图表和设置标题。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 使用文档构建器插入图表形状并获取其图表。
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// 使用“Title”属性给我们的图表一个标题，它出现在图表区域的顶部中心。
ChartTitle title = chart.Title;
title.Text = "My Chart";

 // 将“Show”属性设置为“true”以使标题可见。
title.Show = true;

// 将“Overlay”属性设置为“true”，允许其他图表元素与标题重叠，从而为它们提供更多空间
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


