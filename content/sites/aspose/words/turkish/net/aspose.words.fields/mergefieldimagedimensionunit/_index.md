---
title: Enum MergeFieldImageDimensionUnit
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fields.MergeFieldImageDimensionUnit Sıralama. Adres mektup birleştirme işlemi boyunca kullanılan bir görüntü boyutu birimini yani genişlik veya yükseklik belirtir.
type: docs
weight: 2580
url: /tr/net/aspose.words.fields/mergefieldimagedimensionunit/
---
## MergeFieldImageDimensionUnit enumeration

Adres mektup birleştirme işlemi boyunca kullanılan bir görüntü boyutu birimini (yani genişlik veya yükseklik) belirtir.

```csharp
public enum MergeFieldImageDimensionUnit
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Point | `0` | Nokta (yani 1/72 inç). |
| Percent | `1` | Orijinal resim boyut değerinin yüzdesi. |

### Örnekler

Adres mektup birleştirme sırasında MERGEFIELDS tarafından kabul edildiğinden resimlerin boyutlarının nasıl ayarlanacağını gösterir.

```csharp
{
    Document doc = new Document();

    // Adres mektup birleştirme sırasında bir kaynaktan görüntüleri kabul edecek bir MERGEFIELD ekleyin. Referans için alan kodunu kullanın
    // adres mektup birleştirmede kullanmak istediğimiz görüntülerin yerel sistem dosya adlarını içeren veri kaynağındaki bir sütun.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // Veri kaynağının "ImageColumn" adında böyle bir sütunu olmalıdır.
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // Uygun bir veri kaynağı oluşturun.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add(ImageDir + "Logo.jpg");
    dataTable.Rows.Add(ImageDir + "Transparent background logo.png");
    dataTable.Rows.Add(ImageDir + "Enhanced Windows MetaFile.emf");

    // Birleştirme sırasında görüntülerin boyutlarını değiştirmek için bir geri arama yapılandırın, ardından adres mektup birleştirmeyi yürütün.
    doc.MailMerge.FieldMergingCallback = new MergedImageResizer(200, 200, MergeFieldImageDimensionUnit.Point);
    doc.MailMerge.Execute(dataTable);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.MERGEFIELD.ImageDimension.docx");

/// <summary>
/// Tüm postayla birleştirilmiş resimlerin boyutunu, tanımlanmış bir genişlik ve yüksekliğe ayarlar.
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

### Ayrıca bakınız

* ad alanı [Aspose.Words.Fields](../../aspose.words.fields/)
* toplantı [Aspose.Words](../../)


