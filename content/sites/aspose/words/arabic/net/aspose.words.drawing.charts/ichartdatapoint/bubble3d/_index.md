---
title: IChartDataPoint.Bubble3D
second_title: Aspose.Words لمراجع .NET API
description: IChartDataPoint ملكية. تحديد ما إذا كان يجب تطبيق تأثير ثلاثي الأبعاد للفقاعات في مخطط الفقاعات.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing.charts/ichartdatapoint/bubble3d/
---
## IChartDataPoint.Bubble3D property

تحديد ما إذا كان يجب تطبيق تأثير ثلاثي الأبعاد للفقاعات في مخطط الفقاعات.

```csharp
public bool Bubble3D { get; set; }
```

### أمثلة

يوضح كيفية استخدام التأثيرات ثلاثية الأبعاد مع المخططات الفقاعية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Bubble3D, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);
Assert.True(chart.Series[0].Bubble3D);

// قم بتطبيق ملصق بيانات على كل فقاعة تعرض قطرها.
for (int i = 0; i < 3; i++)
{
    chart.Series[0].HasDataLabels = true;
    chart.Series[0].DataLabels[i].ShowBubbleSize = true;
}

doc.Save(ArtifactsDir + "Charts.Bubble3D.docx");
```

### أنظر أيضا

* interface [IChartDataPoint](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* المجسم [Aspose.Words](../../../)


