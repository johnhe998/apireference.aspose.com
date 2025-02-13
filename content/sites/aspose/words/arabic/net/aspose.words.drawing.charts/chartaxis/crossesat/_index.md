---
title: ChartAxis.CrossesAt
second_title: Aspose.Words لمراجع .NET API
description: ChartAxis ملكية. يحدد مكان تقاطع المحور على المحور العمودي.
type: docs
weight: 50
url: /ar/net/aspose.words.drawing.charts/chartaxis/crossesat/
---
## ChartAxis.CrossesAt property

يحدد مكان تقاطع المحور على المحور العمودي.

```csharp
public double CrossesAt { get; set; }
```

### ملاحظات

الخاصية لها تأثير فقط إذا[`Crosses`](../crosses/) علىCustom. لا تدعمه الرسوم البيانية الجديدة لـ MS Office 2016.

يتم تحديد الوحدات حسب نوع المحور. عندما يكون المحور محور قيمة ، فإن قيمة property هي رقم عشري على محور القيمة. عندما يكون المحور هو محور فئة الوقت ، يتم تعريف القيمة على أنها عدد صحيح من الأيام بالنسبة للتاريخ الأساسي (30/12/1899). بالنسبة لمحور فئة النص ، تكون القيمة رقم فئة عدد صحيح ، بدءًا من 1 كفئة أولى.

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


