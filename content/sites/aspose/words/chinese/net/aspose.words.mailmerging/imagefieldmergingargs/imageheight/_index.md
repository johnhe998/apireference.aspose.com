---
title: ImageFieldMergingArgs.ImageHeight
second_title: Aspose.Words for .NET API 参考
description: ImageFieldMergingArgs 财产. 指定要插入到文档中的图像的图像高度
type: docs
weight: 30
url: /zh/net/aspose.words.mailmerging/imagefieldmergingargs/imageheight/
---
## ImageFieldMergingArgs.ImageHeight property

指定要插入到文档中的图像的图像高度。

```csharp
public MergeFieldImageDimension ImageHeight { get; set; }
```

### 评论

这个属性的值最初来自相应的MERGEFIELD 的代码，包含在 模板文档中。要覆盖初始值，您应该分配一个实例 of [`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/)类到这个属性或为 instance 设置属性[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/)类，由此属性返回。

表示应该应用图像高度的原始值，您应该分配 **无效的** 值到此属性或设置[`Value`](../../../aspose.words.fields/mergefieldimagedimension/value/)instance 的属性[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/)此属性返回的类为负值。

### 例子

显示如何设置图像的尺寸，因为 MERGEFIELDS 在邮件合并期间接受它们。

```csharp
{
    Document doc = new Document();

    // 插入一个 MERGEFIELD，它将在邮件合并期间接受来自源的图像。使用域代码来引用
    // 数据源中的一列，包含我们希望在邮件合并中使用的图像的本地系统文件名。
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // 数据源应该有这样一个名为“ImageColumn”的列。
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // 创建合适的数据源。
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add(ImageDir + "Logo.jpg");
    dataTable.Rows.Add(ImageDir + "Transparent background logo.png");
    dataTable.Rows.Add(ImageDir + "Enhanced Windows MetaFile.emf");

    // 配置回调，在合并时修改图片大小，然后执行邮件合并。
    doc.MailMerge.FieldMergingCallback = new MergedImageResizer(200, 200, MergeFieldImageDimensionUnit.Point);
    doc.MailMerge.Execute(dataTable);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.MERGEFIELD.ImageDimension.docx");

/// <summary>
/// 将所有邮件合并图像的大小设置为一个定义的宽度和高度。
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

### 也可以看看

* class [MergeFieldImageDimension](../../../aspose.words.fields/mergefieldimagedimension/)
* class [ImageFieldMergingArgs](../)
* 命名空间 [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* 部件 [Aspose.Words](../../../)


