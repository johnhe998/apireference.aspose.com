---
title: Table.ClearBorders
second_title: Aspose.Words لمراجع .NET API
description: Table طريقة. يزيل كل حدود الجدول والخلية في هذا الجدول.
type: docs
weight: 370
url: /ar/net/aspose.words.tables/table/clearborders/
---
## Table.ClearBorders method

يزيل كل حدود الجدول والخلية في هذا الجدول.

```csharp
public void ClearBorders()
```

### أمثلة

يوضح كيفية تطبيق حد مخطط تفصيلي على جدول.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// محاذاة الجدول إلى وسط الصفحة.
table.Alignment = TableAlignment.Center;

// امسح أي حدود وتظليل موجود من الجدول.
table.ClearBorders();
table.ClearShading();

// أضف حدودًا خضراء إلى مخطط الجدول.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// املأ الخلايا بلون أخضر فاتح.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

يوضح كيفية إزالة كافة الحدود من جدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

// تعديل لون وسمك الحد العلوي.
Border topBorder = table.FirstRow.RowFormat.Borders[BorderType.Top];
table.SetBorder(BorderType.Top, LineStyle.Double, 1.5, Color.Red, true);

Assert.AreEqual(1.5d, topBorder.LineWidth);
Assert.AreEqual(Color.Red.ToArgb(), topBorder.Color.ToArgb());
Assert.AreEqual(LineStyle.Double, topBorder.LineStyle);

// امسح حدود كل الخلايا في الجدول ، ثم احفظ المستند.
table.ClearBorders();
doc.Save(ArtifactsDir + "Table.ClearBorders.docx");

// تحقق من قيم خصائص الجدول بعد إعادة فتح المستند.
doc = new Document(ArtifactsDir + "Table.ClearBorders.docx");
table = doc.FirstSection.Body.Tables[0];
topBorder = table.FirstRow.RowFormat.Borders[BorderType.Top];

Assert.AreEqual(0.0d, topBorder.LineWidth);
Assert.AreEqual(Color.Empty.ToArgb(), topBorder.Color.ToArgb());
Assert.AreEqual(LineStyle.None, topBorder.LineStyle);
```

### أنظر أيضا

* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


