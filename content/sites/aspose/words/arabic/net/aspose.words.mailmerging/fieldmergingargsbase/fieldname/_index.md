---
title: FieldMergingArgsBase.FieldName
second_title: Aspose.Words لمراجع .NET API
description: FieldMergingArgsBase ملكية. الحصول على اسم حقل الدمج في مصدر البيانات.
type: docs
weight: 40
url: /ar/net/aspose.words.mailmerging/fieldmergingargsbase/fieldname/
---
## FieldMergingArgsBase.FieldName property

الحصول على اسم حقل الدمج في مصدر البيانات.

```csharp
public string FieldName { get; }
```

### ملاحظات

إذا كان لديك تعيين من اسم حقل مستند إلى اسم حقل مصدر بيانات مختلف ، فهذا هو اسم الحقل المعين.

إذا حددت بادئة اسم حقل ، على سبيل المثال "صورة: MyFieldName" في المستند ، ثم **اسم الحقل** إرجاع اسم الحقل بدون البادئة ، وهذا هو "MyFieldName".

### أمثلة

يوضح كيفية إدراج حقول نموذج مربع الاختيار في MERGEFIELDs كبيانات دمج أثناء دمج البريد.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // استخدم MERGEFIELDs مع علامات "TableStart" / "TableEnd" لتعريف منطقة دمج المراسلات
    // الذي ينتمي إلى مصدر بيانات يسمى "StudentCourse" ولديه MERGEFIELD الذي يقبل البيانات من عمود يسمى "CourseName".
    builder.StartTable();
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  TableStart:StudentCourse ");
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  CourseName ");
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  TableEnd:StudentCourse ");
    builder.EndTable();

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertCheckBox();

    DataTable dataTable = GetStudentCourseDataTable();

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMergeEvent.InsertCheckBox.docx");

/// <summary>
/// عند مواجهة MERGEFIELD باسم معين ، يقوم بإدراج حقل نموذج خانة اختيار بدلاً من دمج نص البيانات.
/// </summary>
private class HandleMergeFieldInsertCheckBox : IFieldMergingCallback
{
    /// <summary>
    /// يتم الاستدعاء عندما يقوم دمج المراسلات بدمج البيانات في MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "CourseName")
        {
            Assert.AreEqual("StudentCourse", args.TableName);

            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.FieldName);
            builder.InsertCheckBox(args.DocumentFieldName + mCheckBoxCount, false, 0);

            string fieldValue = args.FieldValue.ToString();

            // في هذه الحالة ، لكل فهرس سجل 'n' قيمة الحقل المقابلة هي "Course n".
            Assert.AreEqual(char.GetNumericValue(fieldValue[7]), args.RecordIndex);

            builder.Write(fieldValue);
            mCheckBoxCount++;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // لا تفعل شيئا.
    }

    private int mCheckBoxCount;
}

/// <summary>
/// ينشئ مصدر بيانات لدمج المراسلات.
/// </summary>
private static DataTable GetStudentCourseDataTable()
{
    DataTable dataTable = new DataTable("StudentCourse");
    dataTable.Columns.Add("CourseName");
    for (int i = 0; i < 10; i++)
    {
        DataRow datarow = dataTable.NewRow();
        dataTable.Rows.Add(datarow);
        datarow[0] = "Course " + i;
    }

    return dataTable;
}
```

### أنظر أيضا

* class [FieldMergingArgsBase](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* المجسم [Aspose.Words](../../../)


