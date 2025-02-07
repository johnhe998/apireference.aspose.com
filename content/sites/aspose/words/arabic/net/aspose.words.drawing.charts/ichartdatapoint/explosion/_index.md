---
title: IChartDataPoint.Explosion
second_title: Aspose.Words لمراجع .NET API
description: IChartDataPoint ملكية. يحدد المقدار الذي يجب نقل نقطة البيانات من مركز الدائرة. يمكن أن تكون سالبة  وتعني السالبة أن الخاصية لم يتم تعيينها ولا يجب تطبيق أي انفجار. ينطبق فقط على المخططات الدائرية .
type: docs
weight: 20
url: /ar/net/aspose.words.drawing.charts/ichartdatapoint/explosion/
---
## IChartDataPoint.Explosion property

يحدد المقدار الذي يجب نقل نقطة البيانات من مركز الدائرة. يمكن أن تكون سالبة ، وتعني السالبة أن الخاصية لم يتم تعيينها ولا يجب تطبيق أي انفجار. ينطبق فقط على المخططات الدائرية .

```csharp
public int Explosion { get; set; }
```

### أمثلة

يوضح كيفية تحريك شرائح المخطط الدائري بعيدًا عن المركز.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Pie, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Sales", chart.Series[0].Name);

قد يتم نقل // شرائح الرسم البياني الدائري بعيدًا عن المركز بمسافة عبر خاصية انفجار نقطة البيانات المعنية.
// أضف نقطة بيانات إلى الجزء الأول من المخطط الدائري وحركه بعيدًا عن المركز بمقدار 10 نقاط.
// Aspose.Words ينشئون نقاط بيانات تلقائيًا إذا لم تكن موجودة.
ChartDataPoint dataPoint = chart.Series[0].DataPoints[0];
dataPoint.Explosion = 10;

// إزاحة الجزء الثاني بمسافة أكبر.
dataPoint = chart.Series[0].DataPoints[1];
dataPoint.Explosion = 40;

doc.Save(ArtifactsDir + "Charts.PieChartExplosion.docx");
```

### أنظر أيضا

* interface [IChartDataPoint](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* المجسم [Aspose.Words](../../../)


