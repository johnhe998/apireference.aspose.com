---
title: FieldBarcode.PostalAddress
second_title: Aspose.Words für .NET-API-Referenz
description: FieldBarcode eigendom. Ermittelt oder setzt die Postanschrift die zum Generieren eines Barcodes verwendet wird oder den Namen des Lesezeichens das darauf verweist.
type: docs
weight: 50
url: /de/net/aspose.words.fields/fieldbarcode/postaladdress/
---
## FieldBarcode.PostalAddress property

Ermittelt oder setzt die Postanschrift, die zum Generieren eines Barcodes verwendet wird, oder den Namen des Lesezeichens, das darauf verweist.

```csharp
public string PostalAddress { get; set; }
```

### Beispiele

Zeigt, wie das Feld BARCODE verwendet wird, um US-Postleitzahlen in Form eines Barcodes anzuzeigen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Im Folgenden finden Sie zwei Möglichkeiten, BARCODE-Felder zu verwenden, um benutzerdefinierte Werte als Barcodes anzuzeigen.
// 1 - Speichern Sie den Wert, den der Barcode in der Eigenschaft "PostalAddress" anzeigt:
FieldBarcode field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);

// Dieser Wert muss eine gültige Postleitzahl sein.
field.PostalAddress = "96801";
field.IsUSPostalAddress = true;
field.FacingIdentificationMark = "C";

Assert.AreEqual(" BARCODE  96801 \\u \\f C", field.GetFieldCode());

builder.InsertBreak(BreakType.LineBreak);

// 2 - Verweisen Sie auf ein Lesezeichen, das den Wert speichert, den dieser Barcode anzeigen wird:
field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);
field.PostalAddress = "BarcodeBookmark";
field.IsBookmark = true;

Assert.AreEqual(" BARCODE  BarcodeBookmark \\b", field.GetFieldCode());

// Das Lesezeichen, auf das das BARCODE-Feld in seiner PostalAddress-Eigenschaft verweist
// darf außer der gültigen Postleitzahl nichts enthalten.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("BarcodeBookmark");
builder.Writeln("968877");
builder.EndBookmark("BarcodeBookmark");

doc.Save(ArtifactsDir + "Field.BARCODE.docx");
```

### Siehe auch

* class [FieldBarcode](../)
* namensraum [Aspose.Words.Fields](../../fieldbarcode/)
* Montage [Aspose.Words](../../../)


