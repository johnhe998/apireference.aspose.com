---
title: ImageFieldMergingArgs.Image
second_title: Aspose.Words لمراجع .NET API
description: ImageFieldMergingArgs ملكية. يحدد الصورة التي يجب على محرك دمج المراسلات إدراجها في المستند.
type: docs
weight: 10
url: /ar/net/aspose.words.mailmerging/imagefieldmergingargs/image/
---
## ImageFieldMergingArgs.Image property

يحدد الصورة التي يجب على محرك دمج المراسلات إدراجها في المستند.

```csharp
public Image Image { get; set; }
```

### أمثلة

يوضح كيفية استخدام رد نداء لتخصيص منطق دمج الصور.

```csharp
{
    Document doc = new Document();

    // أدخل MERGEFIELD الذي سيقبل الصور من مصدر أثناء دمج البريد. استخدم رمز الحقل للرجوع إليه
    // عمود في مصدر البيانات يحتوي على أسماء ملفات النظام المحلي للصور التي نرغب في استخدامها في دمج البريد.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // في هذه الحالة ، يتوقع الحقل أن يكون لمصدر البيانات مثل هذا العمود باسم "ImageColumn".
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // يمكن أن تكون أسماء الملفات طويلة ، وإذا تمكنا من إيجاد طريقة لتجنب تخزينها في مصدر البيانات ،
    // قد نقوم بتقليل حجمه بشكل كبير.
    // إنشاء مصدر بيانات يشير إلى الصور باستخدام أسماء مختصرة.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add("Dark logo");
    dataTable.Rows.Add("Transparent logo");

    // تعيين رد نداء مدمج يحتوي على كل المنطق الذي يعالج تلك الأسماء ،
     // ثم قم بتنفيذ دمج البريد.
    doc.MailMerge.FieldMergingCallback = new ImageFilenameCallback();
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "Field.MERGEFIELD.Images.docx");

/// <summary>
/// يحتوي على قاموس يقوم بتعيين أسماء الصور لأسماء ملفات النظام المحلي التي تحتوي على هذه الصور.
/// إذا كان مصدر بيانات دمج المراسلات يستخدم أحد أسماء القاموس للإشارة إلى صورة ،
/// سيؤدي رد الاتصال هذا إلى تمرير اسم الملف المعني إلى وجهة الدمج.
/// </summary>
private class ImageFilenameCallback : IFieldMergingCallback
{
    public ImageFilenameCallback()
    {
        mImageFilenames = new Dictionary<string, string>();
        mImageFilenames.Add("Dark logo", ImageDir + "Logo.jpg");
        mImageFilenames.Add("Transparent logo", ImageDir + "Transparent background logo.png");
    }

    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        throw new NotImplementedException();
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        if (mImageFilenames.ContainsKey(args.FieldValue.ToString()))
        {
            #if NET48 || JAVA
            args.Image = Image.FromFile(mImageFilenames[args.FieldValue.ToString()]);
            #elif NET5_0_OR_GREATER
            args.Image = SKBitmap.Decode(mImageFilenames[args.FieldValue.ToString()]);
            args.ImageFileName = mImageFilenames[args.FieldValue.ToString()];
            #endif
        }

        Assert.NotNull(args.Image);
    }

    private readonly Dictionary<string, string> mImageFilenames;
}
```

### أنظر أيضا

* class [ImageFieldMergingArgs](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* المجسم [Aspose.Words](../../../)


