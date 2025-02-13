---
title: FieldMergeBarcode.CaseCodeStyle
second_title: Aspose.Words for .NET API Referansı
description: FieldMergeBarcode mülk. Barkod türü ITF14 için Vaka Kodu stilini alır veya ayarlar. Geçerli değerler STDEXTADD
type: docs
weight: 60
url: /tr/net/aspose.words.fields/fieldmergebarcode/casecodestyle/
---
## FieldMergeBarcode.CaseCodeStyle property

Barkod türü ITF14 için Vaka Kodu stilini alır veya ayarlar. Geçerli değerler: [STD&#x7C;EXT&#x7C;ADD]

```csharp
public string CaseCodeStyle { get; set; }
```

### Örnekler

ITF14 barkodlarında adres mektup birleştirmenin nasıl gerçekleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Adres mektup birleştirme sırasında bir veri kaynağından değerleri kabul edecek bir MERGEBARCODE alanı ekleyin.
// Bu alan, bir birleştirme veri kaynağının "MyITF14Barcode" sütunundaki tüm değerleri ITF14 barkodlarına dönüştürecektir.
FieldMergeBarcode field = (FieldMergeBarcode)builder.InsertField(FieldType.FieldMergeBarcode, true);
field.BarcodeType = "ITF14";
field.BarcodeValue = "MyITF14Barcode";
field.CaseCodeStyle = "STD";

Assert.AreEqual(FieldType.FieldMergeBarcode, field.Type);
Assert.AreEqual(" MERGEBARCODE  MyITF14Barcode ITF14 \\c STD", field.GetFieldCode());

// MERGEBARCODE alanımızın BarcodeValue ile aynı ada sahip bir sütunu olan bir DataTable oluşturun.
// Adres mektup birleştirme, her satır için yeni bir sayfa oluşturacaktır. Her sayfa bir EKRAN BARKOD alanı içerecektir,
// birleştirilmiş satırdaki değere sahip bir ITF14 barkodu gösterecek.
DataTable table = new DataTable("Barcodes");
table.Columns.Add("MyITF14Barcode");
table.Rows.Add(new[] { "09312345678907" });
table.Rows.Add(new[] { "1234567891234" });

doc.MailMerge.Execute(table);

Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[0].Type);
Assert.AreEqual("DISPLAYBARCODE \"09312345678907\" ITF14 \\c STD",
    doc.Range.Fields[0].GetFieldCode());
Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[1].Type);
Assert.AreEqual("DISPLAYBARCODE \"1234567891234\" ITF14 \\c STD",
    doc.Range.Fields[1].GetFieldCode());

doc.Save(ArtifactsDir + "Field.MERGEBARCODE.ITF14.docx");
```

### Ayrıca bakınız

* class [FieldMergeBarcode](../)
* ad alanı [Aspose.Words.Fields](../../fieldmergebarcode/)
* toplantı [Aspose.Words](../../../)


