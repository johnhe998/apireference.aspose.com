---
title: MailMerge.PreserveUnusedTags
second_title: Aspose.Words for .NET API Referansı
description: MailMerge mülk. Kullanılmayan bıyık etiketlerinin korunması gerekip gerekmediğini belirten bir değer alır veya ayarlar.
type: docs
weight: 80
url: /tr/net/aspose.words.mailmerging/mailmerge/preserveunusedtags/
---
## MailMerge.PreserveUnusedTags property

Kullanılmayan "bıyık" etiketlerinin korunması gerekip gerekmediğini belirten bir değer alır veya ayarlar.

```csharp
public bool PreserveUnusedTags { get; set; }
```

### Notlar

Varsayılan değer **yanlış** .

### Örnekler

Adres mektup birleştirme sırasında kullanılmayan alternatif adres mektup birleştirme etiketlerinin görünümünün nasıl korunacağını gösterir.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // Varsayılan olarak, adres mektup birleştirme, tablonun her satırındaki verileri, o tablodaki sütunları adlandıran MERGEFIELD'lere yerleştirir. 
    // Belgemizde böyle alanlar yok, ancak küme parantezleri içine alınmış düz metin etiketleri var.
    // "PreserveUnusedTags" bayrağını "true" olarak ayarlarsak, bu etiketleri MERGEFIELD olarak değerlendirebiliriz
    // adres mektup birleştirmemizin bu etiketlerdeki veri kaynağından veri eklemesine izin vermek için.
    // "PreserveUnusedTags" bayrağını "false" olarak ayarlarsak,
    // adres mektup birleştirme bu etiketleri MERGEFIELD'lere dönüştürecek ve onları boş bırakacaktır.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // Belgemizde, tabloda bulunmayan "Sütun2" adlı bir sütun için bir etiket var.
    // "PreserveUnusedTags" bayrağını "false" olarak ayarlarsak, then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Bir belge oluşturun ve adres mektup birleştirme sırasında MERGEFIELD işlevi görebilecek iki düz metin etiketi ekleyin.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // Etiketlerimiz, yalnızca bunu true olarak ayarlarsak adres mektup birleştirme verileri için hedef olarak kaydedilecektir.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Tek sütunlu basit bir veri tablosu oluşturun.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Ayrıca bakınız

* property [UseNonMergeFields](../usenonmergefields/)
* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)


