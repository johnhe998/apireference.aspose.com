---
title: ChartAxis.DisplayUnit
second_title: Aspose.Words لمراجع .NET API
description: ChartAxis ملكية. يحدد قيمة القياس لوحدات العرض لمحور القيمة.
type: docs
weight: 60
url: /ar/net/aspose.words.drawing.charts/chartaxis/displayunit/
---
## ChartAxis.DisplayUnit property

يحدد قيمة القياس لوحدات العرض لمحور القيمة.

```csharp
public AxisDisplayUnit DisplayUnit { get; }
```

### ملاحظات

تؤثر الخاصية على محاور القيمة فقط.

### أمثلة

يوضح كيفية التعامل مع علامات التجزئة والقيم المعروضة لمحور المخطط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// قم بتعيين علامات التجزئة الثانوية للمحور Y للإشارة بعيدًا عن منطقة الرسم ،
// وعلامات التجزئة الرئيسية لعبور المحور.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// اضبط المحور Y لإظهار علامة كبيرة كل 10 وحدات ، وعلامة صغيرة كل 1 وحدة.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// اضبط حدود المحور الصادي على -10 و 20.
// سيعرض المحور Y هذا الآن 4 علامات تجزئة رئيسية و 27 علامة تجزئة ثانوية.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// بالنسبة للمحور السيني ، قم بتعيين علامات التجزئة الرئيسية عند كل 10 وحدات ،
// كل علامة صغيرة عند 2.5 وحدة.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// تكوين كلا النوعين من علامات التجزئة لتظهر داخل منطقة رسم الرسم البياني.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// قم بتعيين حدود المحور X بحيث يمتد المحور X على 5 علامات تجزئة رئيسية و 12 علامة تجزئة ثانوية.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// قم بتعيين علامات التجزئة لعرض قيمتها بالملايين.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// يمكننا تعيين قيمة أكثر تحديدًا والتي من خلالها ستعرض علامات التجزئة قيمها.
// هذا البيان يعادل ما ورد أعلاه.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### أنظر أيضا

* class [AxisDisplayUnit](../../axisdisplayunit/)
* class [ChartAxis](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartaxis/)
* المجسم [Aspose.Words](../../../)


