---
title: Table.SetBorders
second_title: Aspose.Words لمراجع .NET API
description: Table طريقة. تعيين كافة حدود الجدول على نمط الخط والعرض واللون المحدد.
type: docs
weight: 420
url: /ar/net/aspose.words.tables/table/setborders/
---
## Table.SetBorders method

تعيين كافة حدود الجدول على نمط الخط والعرض واللون المحدد.

```csharp
public void SetBorders(LineStyle lineStyle, double lineWidth, Color color)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| lineStyle | LineStyle | نمط الخط المراد تطبيقه. |
| lineWidth | Double | عرض الخط المراد ضبطه (بالنقاط). |
| color | Color | اللون المراد استخدامه للحد. |

### أمثلة

يوضح كيفية تنسيق كل حدود الجدول مرة واحدة.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// مسح كافة الحدود الموجودة من الجدول.
table.ClearBorders();

// قم بتعيين خط أخضر واحد ليكون بمثابة كل حد خارجي وداخلي لهذا الجدول.
table.SetBorders(LineStyle.Single, 1.5, Color.Green);

doc.Save(ArtifactsDir + "Table.SetBorders.docx");
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

* enum [LineStyle](../../../aspose.words/linestyle/)
* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


