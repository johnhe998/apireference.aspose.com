---
title: FieldMergeBarcode.CaseCodeStyle
second_title: Aspose.Words för .NET API Referens
description: FieldMergeBarcode fast egendom. Hämtar eller ställer in stilen för en ärendekod för streckkodstyp ITF14. De giltiga värdena är STDEXTADD
type: docs
weight: 60
url: /sv/net/aspose.words.fields/fieldmergebarcode/casecodestyle/
---
## FieldMergeBarcode.CaseCodeStyle property

Hämtar eller ställer in stilen för en ärendekod för streckkodstyp ITF14. De giltiga värdena är [STD&#x7C;EXT&#x7C;ADD]

```csharp
public string CaseCodeStyle { get; set; }
```

### Exempel

Visar hur man utför en brevkoppling på ITF14 streckkoder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga ett MERGEBARCODE-fält, som kommer att acceptera värden från en datakälla under en e-postkoppling.
// Det här fältet konverterar alla värden i en sammanslagningsdatakällas kolumn "MyITF14Barcode" till ITF14-streckkoder.
FieldMergeBarcode field = (FieldMergeBarcode)builder.InsertField(FieldType.FieldMergeBarcode, true);
field.BarcodeType = "ITF14";
field.BarcodeValue = "MyITF14Barcode";
field.CaseCodeStyle = "STD";

Assert.AreEqual(FieldType.FieldMergeBarcode, field.Type);
Assert.AreEqual(" MERGEBARCODE  MyITF14Barcode ITF14 \\c STD", field.GetFieldCode());

// Skapa en DataTable med en kolumn med samma namn som vårt MERGEBARCODE-fälts BarcodeValue.
// Brevkopplingen skapar en ny sida för varje rad. Varje sida kommer att innehålla ett DISPLAYBARCODE-fält,
// som kommer att visa en ITF14 streckkod med värdet från den sammanslagna raden.
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

### Se även

* class [FieldMergeBarcode](../)
* namnutrymme [Aspose.Words.Fields](../../fieldmergebarcode/)
* hopsättning [Aspose.Words](../../../)


