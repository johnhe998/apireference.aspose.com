---
title: MergeFieldImageDimension.Unit
second_title: Справочник по API Aspose.Words для .NET
description: MergeFieldImageDimension свойство. Единица.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/mergefieldimagedimension/unit/
---
## MergeFieldImageDimension.Unit property

Единица.

```csharp
public MergeFieldImageDimensionUnit Unit { get; set; }
```

### Примеры

Показывает, как установить размеры изображений, поскольку MERGEFIELDS принимает их во время слияния.

```csharp
{
    Document doc = new Document();

    // Вставьте MERGEFIELD, которое будет принимать изображения из источника во время слияния почты. Используйте код поля для ссылки
    // столбец в источнике данных, содержащий локальные системные имена файлов изображений, которые мы хотим использовать при слиянии.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // В источнике данных должен быть такой столбец с именем "ImageColumn".
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // Создадим подходящий источник данных.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add(ImageDir + "Logo.jpg");
    dataTable.Rows.Add(ImageDir + "Transparent background logo.png");
    dataTable.Rows.Add(ImageDir + "Enhanced Windows MetaFile.emf");

    // Настройте обратный вызов для изменения размеров изображений во время слияния, затем выполните слияние.
    doc.MailMerge.FieldMergingCallback = new MergedImageResizer(200, 200, MergeFieldImageDimensionUnit.Point);
    doc.MailMerge.Execute(dataTable);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.MERGEFIELD.ImageDimension.docx");

/// <summary>
/// Устанавливает размер всех изображений, объединенных почтой, в одну определенную ширину и высоту.
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

### Смотрите также

* enum [MergeFieldImageDimensionUnit](../../mergefieldimagedimensionunit/)
* class [MergeFieldImageDimension](../)
* пространство имен [Aspose.Words.Fields](../../mergefieldimagedimension/)
* сборка [Aspose.Words](../../../)


