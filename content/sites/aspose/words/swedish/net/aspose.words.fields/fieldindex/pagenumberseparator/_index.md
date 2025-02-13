---
title: FieldIndex.PageNumberSeparator
second_title: Aspose.Words för .NET API Referens
description: FieldIndex fast egendom. Hämtar eller ställer in teckensekvensen som används för att separera en indexpost och dess sidnummer.
type: docs
weight: 120
url: /sv/net/aspose.words.fields/fieldindex/pagenumberseparator/
---
## FieldIndex.PageNumberSeparator property

Hämtar eller ställer in teckensekvensen som används för att separera en indexpost och dess sidnummer.

```csharp
public string PageNumberSeparator { get; set; }
```

### Exempel

Visar hur man redigerar sidnummeravgränsaren i ett INDEX-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa ett INDEX-fält som visar en post för varje XE-fält som finns i dokumentet.
// Varje post kommer att visa XE-fältets textegenskapsvärde på vänster sida,
// och numret på sidan som innehåller XE-fältet till höger.
// INDEX-posten kommer att gruppera XE-fält med matchande värden i egenskapen "Text"
// i en post i motsats till att göra en post för varje XE-fält.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Om vårt INDEX-fält har en post för en grupp av XE-fält,
// denna post kommer att visa numret på varje sida som innehåller ett XE-fält som tillhör denna grupp.
// Vi kan ställa in anpassade avgränsare för att anpassa utseendet på dessa sidnummer.
index.PageNumberSeparator = ", on page(s) ";
index.PageNumberListSeparator = " & ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\l \" & \"", index.GetFieldCode());
Assert.True(index.HasPageNumberSeparator);

// Efter att vi har infogat dessa XE-fält kommer INDEX-fältet att visa "Första posten, på sida(r) 2 & 3 & 4".
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

Assert.AreEqual(" XE  \"First entry\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageNumberList.docx");
```

### Se även

* class [FieldIndex](../)
* namnutrymme [Aspose.Words.Fields](../../fieldindex/)
* hopsättning [Aspose.Words](../../../)


