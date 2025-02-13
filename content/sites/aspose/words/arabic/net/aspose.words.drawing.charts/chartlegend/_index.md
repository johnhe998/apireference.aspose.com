---
title: Class ChartLegend
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.ChartLegend فصل. يمثل خصائص وسيلة إيضاح الرسم البياني.
type: docs
weight: 680
url: /ar/net/aspose.words.drawing.charts/chartlegend/
---
## ChartLegend class

يمثل خصائص وسيلة إيضاح الرسم البياني.

```csharp
public class ChartLegend
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [LegendEntries](../../aspose.words.drawing.charts/chartlegend/legendentries/) { get; } | إرجاع مجموعة من إدخالات وسيلة الإيضاح لجميع السلاسل وخطوط الاتجاه للمخطط الأصل. |
| [Overlay](../../aspose.words.drawing.charts/chartlegend/overlay/) { get; set; } | تحديد ما إذا كان يُسمح لعناصر المخطط الأخرى بالتداخل مع وسيلة الإيضاح. القيمة الافتراضية هي false . |
| [Position](../../aspose.words.drawing.charts/chartlegend/position/) { get; set; } | تحديد موضع وسيلة الإيضاح على الرسم البياني. القيمة الافتراضية هيRight . |

### أمثلة

يوضح كيفية تحرير مظهر وسيلة إيضاح المخطط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// انقل وسيلة إيضاح الرسم البياني إلى الزاوية اليمنى العليا.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// امنح عناصر المخطط الأخرى ، مثل الرسم البياني ، مساحة أكبر من خلال السماح لهم بالتداخل مع وسيلة الإيضاح.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* المجسم [Aspose.Words](../../)


