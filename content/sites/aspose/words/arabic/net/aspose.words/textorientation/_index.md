---
title: Enum TextOrientation
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.TextOrientation تعداد. يحدد اتجاه النص على الصفحة  في خلية جدول أو إطار نص.
type: docs
weight: 6130
url: /ar/net/aspose.words/textorientation/
---
## TextOrientation enumeration

يحدد اتجاه النص على الصفحة ، في خلية جدول أو إطار نص.

```csharp
public enum TextOrientation
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Horizontal | `0` | يتم ترتيب النص أفقيًا (lr-tb) . |
| Downward | `1` | تم تدوير النص بمقدار 90 درجة جهة اليمين ليظهر من أعلى إلى أسفل (tb-rl) . |
| Upward | `3` | تم تدوير النص 90 درجة إلى اليسار لتظهر من أسفل إلى أعلى (bt-lr) . |
| HorizontalRotatedFarEast | `4` | يتم ترتيب النص أفقيًا ، ولكن يتم تدوير أحرف الشرق الأقصى بمقدار 90 درجة إلى اليسار (lr-tb-v) . |
| VerticalFarEast | `5` | تظهر أحرف الشرق الأقصى بشكل عمودي ، ويتم تدوير النص الآخر بمقدار 90 درجة إلى اليمين لتظهر من أعلى إلى أسفل (tb-rl-v) . |
| VerticalRotatedFarEast | `7` | تظهر أحرف الشرق الأقصى عموديًا ، ويتم تدوير النص الآخر بمقدار 90 درجة إلى اليمين لتظهر من أعلى إلى أسفل عموديًا ، ثم من اليسار إلى اليمين أفقيًا (tb-lr-v) . |

### أمثلة

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

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


