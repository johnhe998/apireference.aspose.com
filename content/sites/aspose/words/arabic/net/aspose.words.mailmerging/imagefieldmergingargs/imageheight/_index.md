---
title: ImageFieldMergingArgs.ImageHeight
second_title: Aspose.Words لمراجع .NET API
description: ImageFieldMergingArgs ملكية. يحدد ارتفاع الصورة للصورة لإدراجها في المستند.
type: docs
weight: 30
url: /ar/net/aspose.words.mailmerging/imagefieldmergingargs/imageheight/
---
## ImageFieldMergingArgs.ImageHeight property

يحدد ارتفاع الصورة للصورة لإدراجها في المستند.

```csharp
public MergeFieldImageDimension ImageHeight { get; set; }
```

### ملاحظات

تأتي قيمة هذه الخاصية مبدئيًا من رمز MERGEFIELD المقابل والموجود في مستند القالب . لتجاوز القيمة الأولية ، يجب عليك تعيين مثيل [`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) فئة لهذه الخاصية أو عيّن الخصائص للمثيل من[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) فئة ، تم إرجاعها بواسطة هذه الخاصية.

للإشارة إلى وجوب تطبيق القيمة الأصلية لارتفاع الصورة ، يجب عليك تعيين ملف **لا شيء** قيمة لهذه الخاصية أو تعيين[`Value`](../../../aspose.words.fields/mergefieldimagedimension/value/) الخاصية للمثيل من[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) الفئة ، التي تم إرجاعها بواسطة هذه الخاصية ، إلى قيمة سالبة.

### أمثلة

يوضح كيفية تعيين أبعاد الصور حيث تقبلها MERGEFIELDS أثناء دمج البريد.

```csharp
{
    Document doc = new Document();

    // أدخل MERGEFIELD الذي سيقبل الصور من مصدر أثناء دمج البريد. استخدم رمز الحقل للرجوع إليه
    // عمود في مصدر البيانات يحتوي على أسماء ملفات النظام المحلي للصور التي نرغب في استخدامها في دمج البريد.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // يجب أن يحتوي مصدر البيانات على عمود يسمى "ImageColumn".
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // إنشاء مصدر بيانات مناسب.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add(ImageDir + "Logo.jpg");
    dataTable.Rows.Add(ImageDir + "Transparent background logo.png");
    dataTable.Rows.Add(ImageDir + "Enhanced Windows MetaFile.emf");

    // تكوين رد اتصال لتعديل أحجام الصور في وقت الدمج ، ثم تنفيذ دمج البريد.
    doc.MailMerge.FieldMergingCallback = new MergedImageResizer(200, 200, MergeFieldImageDimensionUnit.Point);
    doc.MailMerge.Execute(dataTable);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.MERGEFIELD.ImageDimension.docx");

/// <summary>
/// يعين حجم كل الصور المدمجة في البريد على عرض وارتفاع محددين.
/// </summary>
private class MergedImageResizer : IFieldMergingCallback
{
    public MergedImageResizer(double imageWidth, double imageHeight, MergeFieldImageDimensionUnit unit)
    {
        mImageWidth = imageWidth;
        mImageHeight = imageHeight;
        mUnit = unit;
    }

    public void FieldMerging(FieldMergingArgs e)
    {
        throw new NotImplementedException();
    }

    public void ImageFieldMerging(ImageFieldMergingArgs args)
    {
        args.ImageFileName = args.FieldValue.ToString();
        args.ImageWidth = new MergeFieldImageDimension(mImageWidth, mUnit);
        args.ImageHeight = new MergeFieldImageDimension(mImageHeight, mUnit);

        Assert.AreEqual(mImageWidth, args.ImageWidth.Value);
        Assert.AreEqual(mUnit, args.ImageWidth.Unit);
        Assert.AreEqual(mImageHeight, args.ImageHeight.Value);
        Assert.AreEqual(mUnit, args.ImageHeight.Unit);
    }

    private readonly double mImageWidth;
    private readonly double mImageHeight;
    private readonly MergeFieldImageDimensionUnit mUnit;
}
```

### أنظر أيضا

* class [MergeFieldImageDimension](../../../aspose.words.fields/mergefieldimagedimension/)
* class [ImageFieldMergingArgs](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* المجسم [Aspose.Words](../../../)


