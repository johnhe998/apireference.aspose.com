---
title: MailMerge.MergeDuplicateRegions
second_title: Aspose.Words for .NET API Referansı
description: MailMerge mülk. Veri kaynağı adına sahip belge adres mektup birleştirme bölgelerinin tümünün veri kaynağına karşı bölgelerle adres mektup birleştirme yürütülürken mi yoksa yalnızca birinci bölgeyle mi birleştirileceğini belirten bir değer alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.mailmerging/mailmerge/mergeduplicateregions/
---
## MailMerge.MergeDuplicateRegions property

Veri kaynağı adına sahip belge adres mektup birleştirme bölgelerinin tümünün, veri kaynağına karşı bölgelerle adres mektup birleştirme yürütülürken mi yoksa yalnızca birinci bölgeyle mi birleştirileceğini belirten bir değer alır veya ayarlar.

```csharp
public bool MergeDuplicateRegions { get; set; }
```

### Notlar

Varsayılan değer **yanlış** .

### Örnekler

Yinelenen adres mektup birleştirme bölgeleriyle nasıl çalışılacağını gösterir.

```csharp
public void MergeDuplicateRegions(bool mergeDuplicateRegions)
{
    Document doc = CreateSourceDocMergeDuplicateRegions();
    DataTable dataTable = CreateSourceTableMergeDuplicateRegions();

    // "MergeDuplicateRegions" özelliğini "false" olarak ayarlarsak adres mektup birleştirme ilk bölgeyi etkiler,
    // ikincisinin MERGEFIELD'leri birleştirme öncesi durumda kalır.
    // Her iki bölgeyi bu şekilde birleştirmek için,
    // Adres mektup birleştirmeyi aynı adlı bir tabloda iki kez yürütmemiz gerekecekti.
    // "MergeDuplicateRegions" özelliğini "true" olarak ayarlarsak, adres mektup birleştirme her iki bölgeyi de etkiler.
    doc.MailMerge.MergeDuplicateRegions = mergeDuplicateRegions;

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMerge.MergeDuplicateRegions.docx");
}

/// <summary>
/// İki yinelenen adres mektup birleştirme bölgesi içeren bir belge döndürür ("TableStart/End" etiketlerinde aynı adı paylaşır).
/// </summary>
private static Document CreateSourceDocMergeDuplicateRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column1");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");

    return doc;
}

/// <summary>
/// Bir satır ve iki sütun içeren bir veri tablosu oluşturur.
/// </summary>
private static DataTable CreateSourceTableMergeDuplicateRegions()
{
    DataTable dataTable = new DataTable("MergeRegion");
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


