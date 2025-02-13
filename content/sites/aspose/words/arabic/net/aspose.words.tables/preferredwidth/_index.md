---
title: Class PreferredWidth
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Tables.PreferredWidth فصل. يمثل قيمة ووحدة قياسها المستخدمة لتحديد العرض المفضل لجدول أو خلية.
type: docs
weight: 5990
url: /ar/net/aspose.words.tables/preferredwidth/
---
## PreferredWidth class

يمثل قيمة ووحدة قياسها المستخدمة لتحديد العرض المفضل لجدول أو خلية.

```csharp
public sealed class PreferredWidth
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Type](../../aspose.words.tables/preferredwidth/type/) { get; } | الحصول على وحدة القياس المستخدمة لقيمة العرض المفضلة هذه. |
| [Value](../../aspose.words.tables/preferredwidth/value/) { get; } | الحصول على قيمة العرض المفضلة. يتم تحديد وحدة القياس في[`Type`](./type/) الملكية . |

## طُرق

| اسم | وصف |
| --- | --- |
| static [FromPercent](../../aspose.words.tables/preferredwidth/frompercent/)(double) | طريقة إنشاء تقوم بإرجاع مثيل جديد يمثل عرضًا مفضلاً محددًا كنسبة مئوية. |
| static [FromPoints](../../aspose.words.tables/preferredwidth/frompoints/)(double) | طريقة إنشاء تقوم بإرجاع مثيل جديد يمثل العرض المفضل المحدد باستخدام عدد من النقاط. |
| override [Equals](../../aspose.words.tables/preferredwidth/equals/#equals_1)(object) | لتحديد ما إذا كان الكائن المحدد يساوي قيمة الكائن الحالي. |
| [Equals](../../aspose.words.tables/preferredwidth/equals/#equals)(PreferredWidth) | تحديد ما إذا كان PreferredWidth المحدد مساويًا في القيمة لـ PreferredWidth الحالي. |
| override [GetHashCode](../../aspose.words.tables/preferredwidth/gethashcode/)() | يعمل كدالة تجزئة لهذا النوع. |
| override [ToString](../../aspose.words.tables/preferredwidth/tostring/)() | إرجاع سلسلة سهلة الاستخدام تعرض قيمة هذا الكائن. |

## مجالات

| اسم | وصف |
| --- | --- |
| static readonly [Auto](../../aspose.words.tables/preferredwidth/auto/) | إرجاع مثيل يمثل قيمة "العرض المفضل غير محدد". |

### ملاحظات

يمكن تحديد العرض المفضل كنسبة مئوية أو عدد نقاط أو قيمة خاصة "بلا / تلقائي".

حالات هذه الفئة غير قابلة للتغيير.

### أمثلة

يوضح كيفية ضبط الجدول بحيث يتلاءم تلقائيًا مع 50٪ من عرض الصفحة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell #1");
builder.InsertCell();
builder.Write("Cell #2");
builder.InsertCell();
builder.Write("Cell #3");

table.PreferredWidth = PreferredWidth.FromPercent(50);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithPreferredWidth.docx");
```

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

* مساحة الاسم [Aspose.Words.Tables](../../aspose.words.tables/)
* المجسم [Aspose.Words](../../)


