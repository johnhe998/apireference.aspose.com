---
title: MailMerge.MappedDataFields
second_title: Aspose.Words لمراجع .NET API
description: MailMerge ملكية. إرجاع مجموعة تمثل حقول البيانات المعينة لعملية دمج المراسلات.
type: docs
weight: 50
url: /ar/net/aspose.words.mailmerging/mailmerge/mappeddatafields/
---
## MailMerge.MappedDataFields property

إرجاع مجموعة تمثل حقول البيانات المعينة لعملية دمج المراسلات.

```csharp
public MappedDataFieldCollection MappedDataFields { get; }
```

### ملاحظات

تسمح حقول البيانات المعينة بالتعيين تلقائيًا بين أسماء الحقول في مصدر البيانات وأسماء حقول دمج البريد في المستند.

### أمثلة

يوضح كيفية تعيين أعمدة البيانات و MERGEFIELDs بأسماء مختلفة بحيث يتم نقل البيانات بينها أثناء دمج البريد.

```csharp
public void MappedDataFieldCollection()
{
    Document doc = CreateSourceDocMappedDataFields();
    DataTable dataTable = CreateSourceTableMappedDataFields();

    // يحتوي الجدول على عمود يسمى "Column2" ، ولكن لا توجد MERGEFIELDs بهذا الاسم.
    // أيضًا ، لدينا MERGEFIELD يسمى "Column3" ، لكن مصدر البيانات لا يحتوي على عمود بهذا الاسم.
    // إذا كانت البيانات من "Column2" مناسبة لـ "Column3" MERGEFIELD ،
    // يمكننا تعيين اسم العمود هذا إلى MERGEFIELD في زوج المفاتيح / القيمة "MappedDataFields".
    MappedDataFieldCollection mappedDataFields = doc.MailMerge.MappedDataFields;

    // يمكننا ربط اسم عمود مصدر البيانات باسم MERGEFIELD مثل هذا.
    mappedDataFields.Add("MergeFieldName", "DataSourceColumnName");

    // ربط عمود مصدر البيانات المسمى "Column2" بـ MERGEFIELDs المسماة "Column3".
    mappedDataFields.Add("Column3", "Column2");

    // اسم MERGEFIELD هو "مفتاح" اسم عمود مصدر البيانات ذي الصلة "القيمة".
    Assert.AreEqual("DataSourceColumnName", mappedDataFields["MergeFieldName"]);
    Assert.True(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.True(mappedDataFields.ContainsValue("DataSourceColumnName"));

    // الآن إذا قمنا بتشغيل دمج المراسلات هذا ، فستأخذ "Column3" MERGEFIELDs البيانات من "Column2" في الجدول.
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.MappedDataFieldCollection.docx");

    // يمكننا تكرار العناصر الموجودة في هذه المجموعة.
    Assert.AreEqual(2, mappedDataFields.Count);

    using (IEnumerator<KeyValuePair<string, string>> enumerator = mappedDataFields.GetEnumerator())
        while (enumerator.MoveNext())
            Console.WriteLine(
                $"Column named {enumerator.Current.Value} is mapped to MERGEFIELDs named {enumerator.Current.Key}");

    // يمكننا أيضًا إزالة العناصر من المجموعة.
    mappedDataFields.Remove("MergeFieldName");

    Assert.False(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.False(mappedDataFields.ContainsValue("DataSourceColumnName"));

    mappedDataFields.Clear();

    Assert.AreEqual(0, mappedDataFields.Count);
}

/// <summary>
/// أنشئ مستندًا يحتوي على 2 MERGEFIELDs ، أحدهما لا يحتوي على ملف
/// العمود المقابل في جدول البيانات من الطريقة أدناه.
/// </summary>
private static Document CreateSourceDocMappedDataFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column3");

    return doc;
}

/// <summary>
/// أنشئ جدول بيانات من عمودين ، أحدهما لا يحتوي على ملف
/// MERGEFIELD المقابل في المستند المصدر من الطريقة أعلاه.
/// </summary>
private static DataTable CreateSourceTableMappedDataFields()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value1", "Value2" });

    return dataTable;
}
```

### أنظر أيضا

* class [MappedDataFieldCollection](../../mappeddatafieldcollection/)
* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)


