---
title: FieldMergingArgs.Text
second_title: Aspose.Words لمراجع .NET API
description: FieldMergingArgs ملكية. الحصول على أو تعيين النص الذي سيتم إدراجه في المستند لحقل الدمج الحالي.
type: docs
weight: 10
url: /ar/net/aspose.words.mailmerging/fieldmergingargs/text/
---
## FieldMergingArgs.Text property

الحصول على أو تعيين النص الذي سيتم إدراجه في المستند لحقل الدمج الحالي.

```csharp
public string Text { get; set; }
```

### ملاحظات

عندما يتم استدعاء معالج الأحداث الخاص بك ، يتم تعيين هذه الخاصية إلى قيمة خالية.

إذا تركت النص فارغًا ، فسيتم إدراج مشغل دمج المراسلات[`FieldValue`](../../fieldmergingargsbase/fieldvalue/) بدلاً من حقل الدمج.

إذا قمت بتعيين Text إلى أي سلسلة (بما في ذلك الفارغة) ، فسيتم إدراج السلسلة في المستند بدلاً من حقل الدمج.

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

* class [FieldMergingArgs](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../fieldmergingargs/)
* المجسم [Aspose.Words](../../../)


