---
title: IFieldMergingCallback.ImageFieldMerging
second_title: Aspose.Words لمراجع .NET API
description: IFieldMergingCallback طريقة. تم الاستدعاء عندما يكون محرك دمج المراسلات Aspose.Words على وشك إدراج صورة في حقل دمج.
type: docs
weight: 20
url: /ar/net/aspose.words.mailmerging/ifieldmergingcallback/imagefieldmerging/
---
## IFieldMergingCallback.ImageFieldMerging method

تم الاستدعاء عندما يكون محرك دمج المراسلات Aspose.Words على وشك إدراج صورة في حقل دمج.

```csharp
public void ImageFieldMerging(ImageFieldMergingArgs args)
```

### أمثلة

يوضح كيفية إدراج الصور المخزنة في حقل BLOB لقاعدة البيانات في تقرير.

```csharp
public void ImageFromBlob()
{
    Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

    doc.MailMerge.FieldMergingCallback = new HandleMergeImageFieldFromBlob();

    string connString = $"Provider=Microsoft.Jet.OLEDB.4.0;Data Source={DatabaseDir + "Northwind.mdb"};";
    string query = "SELECT FirstName, LastName, Title, Address, City, Region, Country, PhotoBLOB FROM Employees";

    using (OleDbConnection conn = new OleDbConnection(connString))
    {
        conn.Open();

        // افتح قارئ البيانات ، الذي يجب أن يكون في وضع يقرأ جميع السجلات مرة واحدة.
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // لا تفعل شيئا.
    }

    /// <summary>
    /// يتم استدعاء هذا عندما يواجه دمج المراسلات MERGEFIELD في المستند بعلامة "صورة:" في اسمه.
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

### أنظر أيضا

* class [ImageFieldMergingArgs](../../imagefieldmergingargs/)
* interface [IFieldMergingCallback](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../ifieldmergingcallback/)
* المجسم [Aspose.Words](../../../)


