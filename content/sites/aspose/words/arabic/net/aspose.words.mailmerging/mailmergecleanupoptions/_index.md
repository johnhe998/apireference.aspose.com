---
title: Enum MailMergeCleanupOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.MailMerging.MailMergeCleanupOptions تعداد. تحديد الخيارات التي تحدد العناصر التي تتم إزالتها أثناء دمج المراسلات.
type: docs
weight: 3630
url: /ar/net/aspose.words.mailmerging/mailmergecleanupoptions/
---
## MailMergeCleanupOptions enumeration

تحديد الخيارات التي تحدد العناصر التي تتم إزالتها أثناء دمج المراسلات.

```csharp
[Flags]
public enum MailMergeCleanupOptions
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | تحديد قيمة افتراضية . |
| RemoveEmptyParagraphs | `1` | يحدد ما إذا كان يجب إزالة الفقرات التي تحتوي على حقول دمج البريد بدون بيانات من المستند. عند تعيين هذا الخيار ، يتم أيضًا إزالة الفقرات التي تحتوي على حقول دمج بداية ونهاية المنطقة والتي تكون فارغة. |
| RemoveUnusedRegions | `2` | يحدد ما إذا كان يجب إزالة مناطق دمج البريد غير المستخدمة من المستند. |
| RemoveUnusedFields | `4` | تحديد ما إذا كان يجب إزالة حقول الدمج غير المستخدمة من المستند. |
| RemoveContainingFields | `8` | يحدد ما إذا كان يجب إزالة الحقول التي تحتوي على حقول دمج (على سبيل المثال ، IFs) من document إذا تمت إزالة حقول الدمج المتداخلة. |
| RemoveStaticFields | `10` | تحديد ما إذا كان يجب إزالة الحقول الثابتة من المستند. الحقول الثابتة هي الحقول التيتظل النتائج كما هي عند تغيير أي مستند. الحقول التي لا تخزن نتائجها في ملف document ويتم حسابها سريعًا (مثلFieldListNum ، FieldSymbol ، وما إلى ذلك) لا تعتبر ثابتة. |
| RemoveEmptyTableRows | `20` | تحديد ما إذا كان يجب إزالة الصفوف الفارغة التي تحتوي على مناطق دمج المراسلات من المستند. |

### أمثلة

يوضح كيفية إزالة الفقرات الفارغة التي قد ينشئها دمج المراسلات من مستند إخراج الدمج.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD TableStart:MyTable");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertField(" MERGEFIELD TableEnd:MyTable");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "", "" });
dataTable.Rows.Add(new object[] { "Jane", "Doe" });

doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.ExecuteWithRegions(dataTable);

if (doc.MailMerge.CleanupOptions == MailMergeCleanupOptions.RemoveEmptyParagraphs) 
    Assert.AreEqual(
        "John Doe\r" +
        "Jane Doe", doc.GetText().Trim());
else
    Assert.AreEqual(
        "John Doe\r" +
        " \r" +
        "Jane Doe", doc.GetText().Trim());
```

يوضح كيفية إزالة MERGEFIELDs التي لا يتم استخدامها أثناء دمج البريد تلقائيًا.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إنشاء مستند باستخدام MERGEFIELDs لثلاثة أعمدة من جدول مصدر بيانات دمج المراسلات ،
// ثم قم بإنشاء جدول مكون من عمودين فقط تتطابق أسماؤهما مع MERGEFIELDs.
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "Joe", "Bloggs" });

// يشير MERGEFIELD الثالث لدينا إلى عمود "المدينة" ، والذي لا يوجد في مصدر البيانات لدينا.
// سيترك دمج المراسلات حقولًا مثل هذه كما هي في حالة الدمج المسبق الخاصة بها.
// سيؤدي تعيين خاصية "CleanupOptions" على "RemoveUnusedFields" إلى إزالة أية عناصر MERGEFIELD
// التي لا يتم استخدامها أثناء دمج المراسلات لتنظيف مستندات الدمج.
doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.Execute(dataTable);

if (mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveUnusedFields || 
    mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveStaticFields)
    Assert.AreEqual(0, doc.Range.Fields.Count);
else
    Assert.AreEqual(2, doc.Range.Fields.Count);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* المجسم [Aspose.Words](../../)


