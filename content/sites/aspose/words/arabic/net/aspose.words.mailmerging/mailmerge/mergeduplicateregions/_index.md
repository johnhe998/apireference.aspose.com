---
title: MailMerge.MergeDuplicateRegions
second_title: Aspose.Words لمراجع .NET API
description: MailMerge ملكية. الحصول على أو تعيين قيمة تشير إلى ما إذا كان يجب دمج جميع مناطق دمج بريد المستندات مع اسم مصدر البيانات أثناء تنفيذ دمج البريد مع المناطق مقابل مصدر البيانات أو الأول فقط.
type: docs
weight: 60
url: /ar/net/aspose.words.mailmerging/mailmerge/mergeduplicateregions/
---
## MailMerge.MergeDuplicateRegions property

الحصول على أو تعيين قيمة تشير إلى ما إذا كان يجب دمج جميع مناطق دمج بريد المستندات مع اسم مصدر البيانات أثناء تنفيذ دمج البريد مع المناطق مقابل مصدر البيانات أو الأول فقط.

```csharp
public bool MergeDuplicateRegions { get; set; }
```

### ملاحظات

القيمة الافتراضية هي **خاطئة** .

### أمثلة

يوضح كيفية العمل مع مناطق دمج المراسلات المكررة.

```csharp
public void MergeDuplicateRegions(bool mergeDuplicateRegions)
{
    Document doc = CreateSourceDocMergeDuplicateRegions();
    DataTable dataTable = CreateSourceTableMergeDuplicateRegions();

    // إذا قمنا بتعيين خاصية "MergeDuplicateRegions" على "خطأ" ، فسيؤثر دمج البريد على المنطقة الأولى ،
    // بينما سيتم ترك MERGEFIELDs للثاني في حالة ما قبل الدمج.
    // لدمج كلتا المنطقتين هكذا ،
    // سيتعين علينا تنفيذ دمج البريد مرتين على جدول يحمل نفس الاسم.
    // إذا قمنا بتعيين خاصية "MergeDuplicateRegions" على "true" ، فإن دمج البريد سيؤثر على كلا المنطقتين.
    doc.MailMerge.MergeDuplicateRegions = mergeDuplicateRegions;

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMerge.MergeDuplicateRegions.docx");
}

/// <summary>
/// إرجاع مستند يحتوي على منطقتين مكررتين لدمج المراسلات (تشتركان في نفس الاسم في علامتي "TableStart / End").
/// </summary>
private static Document CreateSourceDocMergeDuplicateRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column1");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");

    return doc;
}

/// <summary>
/// ينشئ جدول بيانات بصف واحد وعمودين.
/// </summary>
private static DataTable CreateSourceTableMergeDuplicateRegions()
{
    DataTable dataTable = new DataTable("MergeRegion");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value 1", "Value 2" });

    return dataTable;
}
```

### أنظر أيضا

* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)


