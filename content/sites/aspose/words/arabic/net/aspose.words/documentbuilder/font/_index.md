---
title: DocumentBuilder.Font
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder ملكية. إرجاع كائن يمثل خصائص تنسيق الخط الحالية.
type: docs
weight: 90
url: /ar/net/aspose.words/documentbuilder/font/
---
## DocumentBuilder.Font property

إرجاع كائن يمثل خصائص تنسيق الخط الحالية.

```csharp
public Font Font { get; }
```

### ملاحظات

يستخدم **الخط** للوصول إلى خصائص تنسيق الخط وتعديلها.

حدد تنسيق الخط قبل إدراج النص.

### أمثلة

يوضح كيفية إدراج سلسلة محاطة بحد في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

يوضح كيفية إنشاء جدول منسق باستخدام DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.LeftIndent = 20;

// تعيين بعض خيارات التنسيق لمظهر النص والجدول.
builder.RowFormat.Height = 40;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;

// سيؤدي تكوين خيارات التنسيق في أداة إنشاء المستندات إلى تطبيقها
// إلى الخلية / الصف الحالي الذي يوجد به المؤشر ،
// بالإضافة إلى أي خلايا وصفوف جديدة تم إنشاؤها باستخدام هذا المنشئ.
builder.Write("Header Row,\n Cell 1");
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.Write("Header Row,\n Cell 3");
builder.EndRow();

// إعادة تكوين كائنات التنسيق الخاصة بالباني للصفوف والخلايا الجديدة التي نحن على وشك تكوينها.
// لن يطبق المنشئ هذه على الصف الأول الذي تم إنشاؤه بالفعل بحيث يبرز كصف رأس.
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30;
builder.RowFormat.HeightRule = HeightRule.Auto;
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;

builder.Write("Row 1, Cell 1.");
builder.InsertCell();
builder.Write("Row 1, Cell 2.");
builder.InsertCell();
builder.Write("Row 1, Cell 3.");
builder.EndRow();
builder.InsertCell();
builder.Write("Row 2, Cell 1.");
builder.InsertCell();
builder.Write("Row 2, Cell 2.");
builder.InsertCell();
builder.Write("Row 2, Cell 3.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.CreateFormattedTable.docx");
```

### أنظر أيضا

* class [Font](../../font/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


