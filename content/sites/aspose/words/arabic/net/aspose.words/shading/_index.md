---
title: Class Shading
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Shading فصل. يحتوي على سمات تظليل لكائن .
type: docs
weight: 5690
url: /ar/net/aspose.words/shading/
---
## Shading class

يحتوي على سمات تظليل لكائن .

```csharp
public class Shading : InternableComplexAttr
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [BackgroundPatternColor](../../aspose.words/shading/backgroundpatterncolor/) { get; set; } | الحصول على أو تعيين اللون المطبق على خلفية كائن التظليل. |
| [ForegroundPatternColor](../../aspose.words/shading/foregroundpatterncolor/) { get; set; } | الحصول على أو تعيين اللون المطبق على مقدمة كائن التظليل . |
| [Texture](../../aspose.words/shading/texture/) { get; set; } | الحصول على نسيج التظليل أو تعيينه. |

## طُرق

| اسم | وصف |
| --- | --- |
| [ClearFormatting](../../aspose.words/shading/clearformatting/)() | يزيل التظليل من الكائن . |
| override [Equals](../../aspose.words/shading/equals/#equals_1)(object) | لتحديد ما إذا كان الكائن المحدد يساوي قيمة الكائن الحالي. |
| [Equals](../../aspose.words/shading/equals/#equals)(Shading) | لتحديد ما إذا كان التظليل المحدد مساويًا لقيمة التظليل الحالي. |
| override [GetHashCode](../../aspose.words/shading/gethashcode/)() | يعمل كدالة تجزئة لهذا النوع. |

### أمثلة

يوضح كيفية تزيين النص بالحدود والتظليل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;

Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = Color.LightCoral;
shading.ForegroundPatternColor = Color.LightSalmon;

builder.Write("This paragraph is formatted with a double border and shading.");
doc.Save(ArtifactsDir + "DocumentBuilder.ApplyBordersAndShading.docx");
```

يوضح كيفية تطبيق لون الحدود والتظليل أثناء بناء جدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// بدء جدول وتعيين لون / سمك افتراضي لحدوده.
Table table = builder.StartTable();
table.SetBorders(LineStyle.Single, 2.0, Color.Black);

// إنشاء صف به خليتان بألوان خلفية مختلفة.
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightSkyBlue;
builder.Writeln("Row 1, Cell 1.");
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.Orange;
builder.Writeln("Row 1, Cell 2.");
builder.EndRow();

// إعادة تعيين تنسيق الخلية لتعطيل ألوان الخلفية
// قم بتعيين سماكة حد مخصصة لجميع الخلايا الجديدة التي تم إنشاؤها بواسطة المنشئ ،
// ثم بناء الصف الثاني.
builder.CellFormat.ClearFormatting();
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;

builder.InsertCell();
builder.Writeln("Row 2, Cell 1.");
builder.InsertCell();
builder.Writeln("Row 2, Cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.TableBordersAndShading.docx");
```

### أنظر أيضا

* class [InternableComplexAttr](../internablecomplexattr/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


