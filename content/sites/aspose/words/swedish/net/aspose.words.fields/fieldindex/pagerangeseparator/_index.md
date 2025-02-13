---
title: FieldIndex.PageRangeSeparator
second_title: Aspose.Words för .NET API Referens
description: FieldIndex fast egendom. Hämtar eller ställer in teckensekvensen som används för att separera början och slutet av ett sidintervall.
type: docs
weight: 130
url: /sv/net/aspose.words.fields/fieldindex/pagerangeseparator/
---
## FieldIndex.PageRangeSeparator property

Hämtar eller ställer in teckensekvensen som används för att separera början och slutet av ett sidintervall.

```csharp
public string PageRangeSeparator { get; set; }
```

### Exempel

Visar hur man anger ett bokmärkes spännade sidor som ett sidintervall för en INDEX-fältpost.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa ett INDEX-fält som visar en post för varje XE-fält som finns i dokumentet.
// Varje post kommer att visa XE-fältets textegenskapsvärde på vänster sida,
// och numret på sidan som innehåller XE-fältet till höger.
// INDEX-posten samlar alla XE-fält med matchande värden i egenskapen "Text"
// i en post i motsats till att göra en post för varje XE-fält.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// För INDEX-poster som visar sidintervall kan vi ange en separatorsträng
// som kommer att visas mellan numret på den första sidan och numret på den sista.
index.PageNumberSeparator = ", on page(s) ";
index.PageRangeSeparator = " to ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\g \" to \"", index.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "My entry";

// Om ett XE-fält namnger ett bokmärke med egenskapen PageRangeBookmarkName,
// dess INDEX-post kommer att visa intervallet av sidor som bokmärket sträcker sig över
// istället för numret på sidan som innehåller XE-fältet.
indexEntry.PageRangeBookmarkName = "MyBookmark";

Assert.AreEqual(" XE  \"My entry\" \\r MyBookmark", indexEntry.GetFieldCode());
Assert.AreEqual("MyBookmark", indexEntry.PageRangeBookmarkName);

// Infoga ett bokmärke som börjar på sidan 3 och slutar på sidan 5.
// INDEX-posten för XE-fältet som refererar till detta bokmärke kommer att visa detta sidintervall.
// I vår tabell kommer INDEX-posten att visa "Min post, på sidorna 3 till 5".
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MyBookmark");
builder.Write("Start of MyBookmark");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.Write("End of MyBookmark");
builder.EndBookmark("MyBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageRangeBookmark.docx");
```

### Se även

* class [FieldIndex](../)
* namnutrymme [Aspose.Words.Fields](../../fieldindex/)
* hopsättning [Aspose.Words](../../../)


