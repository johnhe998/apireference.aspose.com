---
title: DocumentBuilder.EndRow
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. إنهاء صف جدول في المستند.
type: docs
weight: 220
url: /ar/net/aspose.words/documentbuilder/endrow/
---
## DocumentBuilder.EndRow method

إنهاء صف جدول في المستند.

```csharp
public Row EndRow()
```

### قيمة الإرجاع

عقدة الصف التي تم الانتهاء منها للتو.

### ملاحظات

مكالمة **EndRow** لإنهاء صف الجدول. إذا اتصلت[`InsertCell`](../insertcell/) على الفور بعد ذلك ، ثم يستمر الجدول في صف جديد.

استخدم ال[`RowFormat`](../rowformat/) خاصية لتحديد تنسيق الصف.

### أمثلة

يوضح كيفية دمج خلايا الجدول عموديًا.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل خلية في العمود الأول من الصف الأول.
// ستكون هذه الخلية الأولى في نطاق الخلايا المدمجة عموديًا.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// أدخل خلية في العمود الثاني من الصف الأول ، ثم قم بإنهاء الصف.
// أيضًا ، قم بتكوين المنشئ لتعطيل الدمج الرأسي في الخلايا التي تم إنشاؤها.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();

// أدخل خلية في العمود الأول من الصف الثاني. 
// بدلاً من إضافة محتويات نصية ، سنقوم بدمج هذه الخلية مع الخلية الأولى التي أضفناها أعلاه مباشرةً.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// أدخل خلية مستقلة أخرى في العمود الثاني من الصف الثاني.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.VerticalMerge.docx");
```

يوضح كيفية إنشاء جدول منسق بحجم 2 × 2.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndRow();

// أثناء بناء الجدول ، سيقوم منشئ الوثيقة بتطبيق قيم خاصية RowFormat / CellFormat الحالية
// إلى الصف / الخلية الحالية التي يوجد بها المؤشر وأي صفوف / خلايا جديدة أثناء إنشائها.
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[0].CellFormat.VerticalAlignment);
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[1].CellFormat.VerticalAlignment);

builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 2, cell 1.");
builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 2, cell 2.");
builder.EndRow();
builder.EndTable();

// لا تتأثر الصفوف والخلايا المضافة مسبقًا بأثر رجعي بالتغييرات في تنسيق المنشئ.
Assert.AreEqual(0, table.Rows[0].RowFormat.Height);
Assert.AreEqual(HeightRule.Auto, table.Rows[0].RowFormat.HeightRule);
Assert.AreEqual(100, table.Rows[1].RowFormat.Height);
Assert.AreEqual(HeightRule.Exactly, table.Rows[1].RowFormat.HeightRule);
Assert.AreEqual(TextOrientation.Upward, table.Rows[1].Cells[0].CellFormat.Orientation);
Assert.AreEqual(TextOrientation.Downward, table.Rows[1].Cells[1].CellFormat.Orientation);

doc.Save(ArtifactsDir + "DocumentBuilder.BuildTable.docx");
```

يوضح كيفية إنشاء جدول بحدود مخصصة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

// تعيين خيارات تنسيق الجدول لمنشئ المستندات
// سيطبقها على كل صف وخلية نضيفها معها.
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.CellFormat.ClearFormatting();
builder.CellFormat.Width = 150;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.CellFormat.Shading.BackgroundPatternColor = Color.GreenYellow;
builder.CellFormat.WrapText = false;
builder.CellFormat.FitText = true;

builder.RowFormat.ClearFormatting();
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.RowFormat.Height = 50;
builder.RowFormat.Borders.LineStyle = LineStyle.Engrave3D;
builder.RowFormat.Borders.Color = Color.Orange;

builder.InsertCell();
builder.Write("Row 1, Col 1");

builder.InsertCell();
builder.Write("Row 1, Col 2");
builder.EndRow();

// سيؤدي تغيير التنسيق إلى تطبيقه على الخلية الحالية ،
// وأي خلايا جديدة ننشئها باستخدام المنشئ بعد ذلك.
// لن يؤثر هذا على الخلايا التي أضفناها سابقًا.
builder.CellFormat.Shading.ClearFormatting();

builder.InsertCell();
builder.Write("Row 2, Col 1");

builder.InsertCell();
builder.Write("Row 2, Col 2");

builder.EndRow();

// زيادة ارتفاع الصف ليناسب النص الرأسي.
builder.InsertCell();
builder.RowFormat.Height = 150;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 3, Col 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 3, Col 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTable.docx");
```

### أنظر أيضا

* class [Row](../../../aspose.words.tables/row/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


