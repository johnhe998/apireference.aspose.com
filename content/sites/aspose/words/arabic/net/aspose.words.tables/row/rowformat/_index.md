---
title: Row.RowFormat
second_title: Aspose.Words لمراجع .NET API
description: Row ملكية. يوفر الوصول إلى خصائص تنسيق الصف.
type: docs
weight: 90
url: /ar/net/aspose.words.tables/row/rowformat/
---
## Row.RowFormat property

يوفر الوصول إلى خصائص تنسيق الصف.

```csharp
public RowFormat RowFormat { get; }
```

### أمثلة

يوضح كيفية تعديل تنسيق صف الجدول.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// استخدم خاصية "RowFormat" للصف الأول لتعيين التنسيق الذي يعدل مظهر الصف بأكمله.
Row firstRow = table.FirstRow;
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;

doc.Save(ArtifactsDir + "Table.RowFormat.docx");
```

يوضح كيفية تعديل تنسيق الصفوف والخلايا في جدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("City");
builder.InsertCell();
builder.Write("Country");
builder.EndRow();
builder.InsertCell();
builder.Write("London");
builder.InsertCell();
builder.Write("U.K.");
builder.EndTable();

// استخدم خاصية "RowFormat" للصف الأول لتعديل التنسيق
// من محتويات جميع الخلايا في هذا الصف.
RowFormat rowFormat = table.FirstRow.RowFormat;
rowFormat.Height = 25;
rowFormat.Borders[BorderType.Bottom].Color = Color.Red;

// استخدم خاصية "CellFormat" للخلية الأولى في الصف الأخير لتعديل تنسيق محتويات تلك الخلية.
CellFormat cellFormat = table.LastRow.FirstCell.CellFormat;
cellFormat.Width = 100;
cellFormat.Shading.BackgroundPatternColor = Color.Orange;

doc.Save(ArtifactsDir + "Table.RowCellFormat.docx");
```

### أنظر أيضا

* class [RowFormat](../../rowformat/)
* class [Row](../)
* مساحة الاسم [Aspose.Words.Tables](../../row/)
* المجسم [Aspose.Words](../../../)


