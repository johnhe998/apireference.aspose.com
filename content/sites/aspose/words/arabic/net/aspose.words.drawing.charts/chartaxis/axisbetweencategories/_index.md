---
title: ChartAxis.AxisBetweenCategories
second_title: Aspose.Words لمراجع .NET API
description: ChartAxis ملكية. الحصول على أو تعيين علامة تشير إلى ما إذا كان محور القيمة يتقاطع مع محور الفئة بين الفئات.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing.charts/chartaxis/axisbetweencategories/
---
## ChartAxis.AxisBetweenCategories property

الحصول على أو تعيين علامة تشير إلى ما إذا كان محور القيمة يتقاطع مع محور الفئة بين الفئات.

```csharp
public bool AxisBetweenCategories { get; set; }
```

### ملاحظات

الخاصية لها تأثير فقط على محاور القيمة. لا يتم دعمه بواسطة مخططات MS Office 2016 الجديدة .

### أمثلة

يوضح كيفية عبور محور الرسم البياني في موقع مخصص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// بالنسبة إلى المخططات العمودية ، يتقاطع المحور ص عند الصفر افتراضيًا ،
// مما يعني أن الأعمدة لجميع القيم أقل من الصفر تشير إلى الأسفل لتمثل القيم السالبة.
// يمكننا تعيين قيمة مختلفة لعبور المحور ص. في هذه الحالة ، سنضبطه على 3.
ChartAxis axis = chart.AxisX;
axis.Crosses = AxisCrosses.Custom;
axis.CrossesAt = 3;
axis.AxisBetweenCategories = true;

doc.Save(ArtifactsDir + "Charts.AxisCross.docx");
```

### أنظر أيضا

* class [ChartAxis](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartaxis/)
* المجسم [Aspose.Words](../../../)


