---
title: Class FieldMergingArgs
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.MailMerging.FieldMergingArgs فصل. توفير بيانات لملف مجال مدمج الحدث .
type: docs
weight: 3550
url: /ar/net/aspose.words.mailmerging/fieldmergingargs/
---
## FieldMergingArgs class

توفير بيانات لملف **مجال مدمج** الحدث .

```csharp
public class FieldMergingArgs : FieldMergingArgsBase
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Document](../../aspose.words.mailmerging/fieldmergingargsbase/document/) { get; } | إرجاع ملف[`Document`](../fieldmergingargsbase/document/) الكائن الذي يتم تنفيذ دمج المراسلات. |
| [DocumentFieldName](../../aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/) { get; } | الحصول على اسم حقل الدمج كما هو محدد في المستند. |
| [Field](../../aspose.words.mailmerging/fieldmergingargsbase/field/) { get; } | الحصول على الكائن الذي يمثل حقل الدمج الحالي. |
| [FieldName](../../aspose.words.mailmerging/fieldmergingargsbase/fieldname/) { get; } | الحصول على اسم حقل الدمج في مصدر البيانات. |
| [FieldValue](../../aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/) { get; set; } | الحصول على أو تعيين قيمة الحقل من مصدر البيانات. |
| [RecordIndex](../../aspose.words.mailmerging/fieldmergingargsbase/recordindex/) { get; } | الحصول على فهرس السجل الذي يتم دمجه على أساس الصفر. |
| [TableName](../../aspose.words.mailmerging/fieldmergingargsbase/tablename/) { get; } | الحصول على اسم جدول البيانات لعملية الدمج الحالية أو السلسلة الفارغة إذا لم يكن الاسم متاحًا . |
| [Text](../../aspose.words.mailmerging/fieldmergingargs/text/) { get; set; } | الحصول على أو تعيين النص الذي سيتم إدراجه في المستند لحقل الدمج الحالي. |

### ملاحظات

ال **مجال مدمج** حدث أثناء دمج المراسلات عند مصادفة حقل merge بسيط في المستند. يمكنك الرد على هذا الحدث لإرجاع نص لمحرك دمج المراسلات لإدراجه في المستند.

### أمثلة

يوضح كيفية تنفيذ دمج المراسلات باستخدام رد اتصال مخصص يعالج بيانات الدمج في شكل مستندات HTML.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(@"MERGEFIELD  html_Title  \b Content");
    builder.InsertField(@"MERGEFIELD  html_Body  \b Content");

    object[] mergeData =
    {
        "<html>" +
            "<h1>" +
                "<span style=\"color: #0000ff; font-family: Arial;\">Hello World!</span>" +
            "</h1>" +
        "</html>", 

        "<html>" +
            "<blockquote>" +
                "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>" +
            "</blockquote>" +
        "</html>"
    };

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertHtml();
    doc.MailMerge.Execute(new[] { "html_Title", "html_Body" }, mergeData);

    doc.Save(ArtifactsDir + "MailMergeEvent.MergeHtml.docx");
}

/// <summary>
/// إذا واجه دمج البريد MERGEFIELD يبدأ اسمه بالبادئة "html_" ،
/// هذا الاستدعاء يحلل بيانات الدمج الخاصة به كمحتوى HTML ويضيف النتيجة إلى موقع المستند الخاص بـ MERGEFIELD.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// يتم الاستدعاء عندما يقوم دمج المراسلات بدمج البيانات في MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // أضف بيانات HTML التي تم تحليلها إلى نص المستند.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // نظرًا لأننا أدخلنا المحتوى المدمج يدويًا بالفعل ،
             // لن نحتاج إلى الرد على هذا الحدث من خلال إعادة المحتوى عبر خاصية "النص".
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // لا تفعل شيئا.
    }
}
```

### أنظر أيضا

* class [FieldMergingArgsBase](../fieldmergingargsbase/)
* مساحة الاسم [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* المجسم [Aspose.Words](../../)


