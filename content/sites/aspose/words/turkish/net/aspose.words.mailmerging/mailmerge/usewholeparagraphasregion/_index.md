---
title: MailMerge.UseWholeParagraphAsRegion
second_title: Aspose.Words for .NET API Referansı
description: MailMerge mülk. TableStart veya TableEnd field ile tüm paragrafın mı yoksa TableStart ve TableEnd alanları arasındaki belirli aralığın adres mektup birleştirme bölgesine dahil edilip edilmeyeceğini belirten bir değer alır veya ayarlar.
type: docs
weight: 160
url: /tr/net/aspose.words.mailmerging/mailmerge/usewholeparagraphasregion/
---
## MailMerge.UseWholeParagraphAsRegion property

TableStart veya TableEnd field ile tüm paragrafın mı yoksa TableStart ve TableEnd alanları arasındaki belirli aralığın adres mektup birleştirme bölgesine dahil edilip edilmeyeceğini belirten bir değer alır veya ayarlar.

```csharp
public bool UseWholeParagraphAsRegion { get; set; }
```

### Notlar

Varsayılan değer **doğru** .

### Örnekler

Adres mektup birleştirme bölgeleri ve paragraflar arasındaki ilişkiyi gösterir.

```csharp
public void UseWholeParagraphAsRegion(bool useWholeParagraphAsRegion)
{
    Document doc = CreateSourceDocWithNestedMergeRegions();
    DataTable dataTable = CreateSourceTableDataTableForOneRegion();

    // Varsayılan olarak, bir paragraf birden fazla adres mektup birleştirme bölgesine ait olamaz.
    // Belgemizin içeriği bu kriterleri karşılamıyor.
    // "UseWholeParagraphAsRegion" bayrağını "true" olarak ayarlarsak,
    // bu belgede adres mektup birleştirmeyi çalıştırmak bir istisna oluşturur.
    // "UseWholeParagraphAsRegion" bayrağını "false" olarak ayarlarsak,
    // bu belge üzerinde adres mektup birleştirme gerçekleştirebileceğiz.
    doc.MailMerge.UseWholeParagraphAsRegion = useWholeParagraphAsRegion;

    if (useWholeParagraphAsRegion)
        Assert.Throws<InvalidOperationException>(() => doc.MailMerge.ExecuteWithRegions(dataTable));
    else
        doc.MailMerge.ExecuteWithRegions(dataTable);

    // Adres mektup birleştirme, ikinci bölgeyi kullanılmadan bırakırken ilk bölgemizi doldurur
    // kuralı bozan bölge olduğu için.
    doc.Save(ArtifactsDir + "MailMerge.UseWholeParagraphAsRegion.docx");
}

/// <summary>
/// Bir paragrafı paylaşan iki adres mektup birleştirme bölgesi içeren bir belge oluşturun.
/// </summary>
private static Document CreateSourceDocWithNestedMergeRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Region 1: ");
    builder.InsertField(" MERGEFIELD TableStart:MyTable");
    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    builder.Write(", Region 2: ");
    builder.InsertField(" MERGEFIELD TableStart:MyOtherTable");
    builder.InsertField(" MERGEFIELD TableEnd:MyOtherTable");

    return doc;
}

/// <summary>
/// Adres mektup birleştirme sırasında bir bölgeyi doldurabilen bir veri tablosu oluşturun.
/// </summary>
private static DataTable CreateSourceTableDataTableForOneRegion()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value 1", "Value 2" });

    return dataTable;
}
```

### Ayrıca bakınız

* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)


