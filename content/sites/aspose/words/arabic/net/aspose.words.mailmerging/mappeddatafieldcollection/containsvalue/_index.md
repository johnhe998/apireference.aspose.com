---
title: MappedDataFieldCollection.ContainsValue
second_title: Aspose.Words لمراجع .NET API
description: MappedDataFieldCollection طريقة. تحديد ما إذا كان التعيين من الحقل المحدد في مصدر البيانات موجودًا في المجموعة.
type: docs
weight: 60
url: /ar/net/aspose.words.mailmerging/mappeddatafieldcollection/containsvalue/
---
## MappedDataFieldCollection.ContainsValue method

تحديد ما إذا كان التعيين من الحقل المحدد في مصدر البيانات موجودًا في المجموعة.

```csharp
public bool ContainsValue(string dataSourceFieldName)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| dataSourceFieldName | String | اسم حساس لحالة الأحرف للحقل في مصدر البيانات. |

### قيمة الإرجاع

صحيح إذا تم العثور على العنصر في المجموعة ؛ خلاف ذلك ، خطأ.

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

* class [MappedDataFieldCollection](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mappeddatafieldcollection/)
* المجسم [Aspose.Words](../../../)


