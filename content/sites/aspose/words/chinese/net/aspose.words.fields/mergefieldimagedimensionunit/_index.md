---
title: Enum MergeFieldImageDimensionUnit
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.MergeFieldImageDimensionUnit 枚举. 指定邮件合并过程中使用的图像尺寸单位即宽度或高度
type: docs
weight: 2580
url: /zh/net/aspose.words.fields/mergefieldimagedimensionunit/
---
## MergeFieldImageDimensionUnit enumeration

指定邮件合并过程中使用的图像尺寸单位（即宽度或高度）。

```csharp
public enum MergeFieldImageDimensionUnit
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Point | `0` | 点（即 1/72 英寸）。 |
| Percent | `1` | 原始图像尺寸值的百分比。 |

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

* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


