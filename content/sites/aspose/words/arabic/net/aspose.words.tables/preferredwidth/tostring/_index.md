---
title: PreferredWidth.ToString
second_title: Aspose.Words لمراجع .NET API
description: PreferredWidth طريقة. إرجاع سلسلة سهلة الاستخدام تعرض قيمة هذا الكائن.
type: docs
weight: 80
url: /ar/net/aspose.words.tables/preferredwidth/tostring/
---
## PreferredWidth.ToString method

إرجاع سلسلة سهلة الاستخدام تعرض قيمة هذا الكائن.

```csharp
public override string ToString()
```

### أمثلة

يوضح كيفية تعيين العرض المفضل لخلايا الجدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// هناك طريقتان لتطبيق فئة "PreferredWidth" على خلايا الجدول.
// 1 - قم بتعيين عرض مفضل مطلق بناءً على النقاط:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - قم بتعيين عرض مفضل نسبي بناءً على النسبة المئوية لعرض الجدول:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// ستشغل الخلية التي ليس لها عرض مفضل محدد بقية المساحة المتاحة.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// ينشئ كل تكوين للخاصية "PreferredWidth" كائنًا جديدًا.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### أنظر أيضا

* class [PreferredWidth](../)
* مساحة الاسم [Aspose.Words.Tables](../../preferredwidth/)
* المجسم [Aspose.Words](../../../)


