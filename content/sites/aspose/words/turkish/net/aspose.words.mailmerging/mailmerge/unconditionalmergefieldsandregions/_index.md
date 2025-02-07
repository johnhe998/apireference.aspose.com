---
title: MailMerge.UnconditionalMergeFieldsAndRegions
second_title: Aspose.Words for .NET API Referansı
description: MailMerge mülk. Üst EĞER alanının koşulundan bağımsız olarak birleştirme alanlarının ve birleştirme bölgelerinin birleştirilip birleştirilmediğini gösteren bir değer alır veya ayarlar.
type: docs
weight: 140
url: /tr/net/aspose.words.mailmerging/mailmerge/unconditionalmergefieldsandregions/
---
## MailMerge.UnconditionalMergeFieldsAndRegions property

Üst EĞER alanının koşulundan bağımsız olarak birleştirme alanlarının ve birleştirme bölgelerinin birleştirilip birleştirilmediğini gösteren bir değer alır veya ayarlar.

```csharp
public bool UnconditionalMergeFieldsAndRegions { get; set; }
```

### Notlar

Varsayılan değer **yanlış** .

### Örnekler

Üst EĞER alanının koşulundan bağımsız olarak alanların veya bölgelerin nasıl birleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// EĞER alanının içine yerleştirilmiş bir MERGEFIELD ekleyin.
// IF alan ifadesi yanlış olduğundan, MERGEFIELD sonucunu görüntülemeyecektir.
// MERGEFIELD, adres mektup birleştirme sırasında da herhangi bir veri almaz.
FieldIf fieldIf = (FieldIf)builder.InsertField(" IF 1 = 2 ");
builder.MoveTo(fieldIf.Separator);
builder.InsertField(" MERGEFIELD  FullName ");

// "UnconditionalMergeFieldsAndRegions" bayrağını "true" olarak ayarlarsak,
// adres mektup birleştirmemiz, diğerlerinin yanı sıra MERGEFIELD gibi görüntülenmeyen alanlara veri ekleyecektir.
// "UnconditionalMergeFieldsAndRegions" bayrağını "false" olarak ayarlarsak,
// adres mektup birleştirmemiz, yanlış ifadeler içeren IF alanları tarafından gizlenen MERGEFIELD'lere veri eklemeyecektir.
doc.MailMerge.UnconditionalMergeFieldsAndRegions = countAllMergeFields;

DataTable dataTable = new DataTable();
dataTable.Columns.Add("FullName");
dataTable.Rows.Add("James Bond");

doc.MailMerge.Execute(dataTable);

doc.Save(ArtifactsDir + "MailMerge.UnconditionalMergeFieldsAndRegions.docx");

Assert.AreEqual(
    countAllMergeFields
        ? "\u0013 IF 1 = 2 \"James Bond\"\u0014\u0015"
        : "\u0013 IF 1 = 2 \u0013 MERGEFIELD  FullName \u0014«FullName»\u0015\u0014\u0015",
    doc.GetText().Trim());
```

### Ayrıca bakınız

* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)


