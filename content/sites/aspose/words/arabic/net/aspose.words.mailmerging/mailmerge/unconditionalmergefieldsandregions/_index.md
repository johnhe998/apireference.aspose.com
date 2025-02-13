---
title: MailMerge.UnconditionalMergeFieldsAndRegions
second_title: Aspose.Words لمراجع .NET API
description: MailMerge ملكية. الحصول على أو تعيين قيمة تشير إلى ما إذا كانت حقول الدمج ومناطق الدمج مدمجة بغض النظر عن حالة حقل IF الأصلي.
type: docs
weight: 140
url: /ar/net/aspose.words.mailmerging/mailmerge/unconditionalmergefieldsandregions/
---
## MailMerge.UnconditionalMergeFieldsAndRegions property

الحصول على أو تعيين قيمة تشير إلى ما إذا كانت حقول الدمج ومناطق الدمج مدمجة بغض النظر عن حالة حقل IF الأصلي.

```csharp
public bool UnconditionalMergeFieldsAndRegions { get; set; }
```

### ملاحظات

القيمة الافتراضية هي **خاطئة** .

### أمثلة

يُظهر كيفية دمج الحقول أو المناطق بغض النظر عن شرط حقل IF الأصلي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل MERGEFIELD متداخلًا داخل حقل IF.
// نظرًا لأن بيان الحقل IF خاطئ ، فلن يعرض نتيجة MERGEFIELD.
// لن يتلقى MERGEFIELD أيضًا أي بيانات أثناء دمج البريد.
FieldIf fieldIf = (FieldIf)builder.InsertField(" IF 1 = 2 ");
builder.MoveTo(fieldIf.Separator);
builder.InsertField(" MERGEFIELD  FullName ");

// إذا قمنا بتعيين علامة "UnconditionalMergeFieldsAndRegions" على "true" ،
// سيقوم دمج البريد لدينا بإدراج البيانات في الحقول غير المعروضة مثل MERGEFIELD الخاص بنا بالإضافة إلى جميع الحقول الأخرى.
// إذا قمنا بتعيين علامة "UnconditionalMergeFieldsAndRegions" على "false" ،
// لن يقوم دمج البريد بإدراج البيانات في MERGEFIELDs المخفية بواسطة حقول IF ببيانات خاطئة.
doc.MailMerge.UnconditionalMergeFieldsAndRegions = countAllMergeFields;

DataTable dataTable = new DataTable();
dataTable.Columns.Add("FullName");
dataTable.Rows.Add("James Bond");

doc.MailMerge.Execute(dataTable);

doc.Save(ArtifactsDir + "MailMerge.UnconditionalMergeFieldsAndRegions.docx");

Assert.AreEqual(
    countAllMergeFields
        ? "\u0013 IF 1 = 2 \"James Bond\"\u0014\u0015"
        : "\u0013 IF 1 = 2 \u0013 MERGEFIELD  FullName \u0014«FullName»\u0015\u0014\u0015",
    doc.GetText().Trim());
```

### أنظر أيضا

* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)


