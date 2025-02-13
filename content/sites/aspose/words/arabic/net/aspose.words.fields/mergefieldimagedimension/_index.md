---
title: Class MergeFieldImageDimension
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.MergeFieldImageDimension فصل. يمثل بُعد الصورة أي العرض أو الارتفاع المستخدم عبر عملية دمج المراسلات.
type: docs
weight: 2570
url: /ar/net/aspose.words.fields/mergefieldimagedimension/
---
## MergeFieldImageDimension class

يمثل بُعد الصورة (أي العرض أو الارتفاع) المستخدم عبر عملية دمج المراسلات.

```csharp
public class MergeFieldImageDimension
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [MergeFieldImageDimension](mergefieldimagedimension/#constructor)(double) | ينشئ مثيلًا لأبعاد الصورة بالقيمة المحددة بالنقاط. |
| [MergeFieldImageDimension](mergefieldimagedimension/#constructor_1)(double, MergeFieldImageDimensionUnit) | ينشئ مثيلًا لأبعاد الصورة بالقيمة المحددة والوحدة المحددة. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Unit](../../aspose.words.fields/mergefieldimagedimension/unit/) { get; set; } | الوحدة . |
| [Value](../../aspose.words.fields/mergefieldimagedimension/value/) { get; set; } | القيمة . |

### ملاحظات

للإشارة إلى أنه يجب إدراج الصورة بأبعادها الأصلية أثناء دمج المراسلات ، يجب عليك تعيين قيمة سالبة إلى[`Value`](./value/) الملكية .

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

* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


