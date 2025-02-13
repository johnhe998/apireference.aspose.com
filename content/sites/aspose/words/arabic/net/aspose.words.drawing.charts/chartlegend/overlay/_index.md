---
title: ChartLegend.Overlay
second_title: Aspose.Words لمراجع .NET API
description: ChartLegend ملكية. تحديد ما إذا كان يُسمح لعناصر المخطط الأخرى بالتداخل مع وسيلة الإيضاح. القيمة الافتراضية هي false .
type: docs
weight: 20
url: /ar/net/aspose.words.drawing.charts/chartlegend/overlay/
---
## ChartLegend.Overlay property

تحديد ما إذا كان يُسمح لعناصر المخطط الأخرى بالتداخل مع وسيلة الإيضاح. القيمة الافتراضية هي false .

```csharp
public bool Overlay { get; set; }
```

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

* class [ChartLegend](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartlegend/)
* المجسم [Aspose.Words](../../../)


