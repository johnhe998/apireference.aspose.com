---
title: FieldXE.EntryType
second_title: Aspose.Words för .NET API Referens
description: FieldXE fast egendom. Hämtar eller ställer in en indexposttyp.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldxe/entrytype/
---
## FieldXE.EntryType property

Hämtar eller ställer in en indexposttyp.

```csharp
public string EntryType { get; set; }
```

### Exempel

Visar hur man skapar ett INDEX-fält och sedan använder XE-fält för att fylla i det med poster.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa ett INDEX-fält som visar en post för varje XE-fält som finns i dokumentet.
// Varje post kommer att visa XE-fältets Text-egenskapsvärde på vänster sida
// och sidan som innehåller XE-fältet till höger.
// Om XE-fälten har samma värde i egenskapen "Text",
// INDEX-fältet grupperar dem i en post.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Konfigurera INDEX-fältet för att endast visa XE-fält som ligger inom gränserna
// av ett bokmärke som heter "MainBookmark", och vars "EntryType"-egenskaper har värdet "A".
// För både INDEX- och XE-fält använder egenskapen "EntryType" endast det första tecknet i dess strängvärde.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// På en ny sida börjar du bokmärket med ett namn som matchar värdet
// av INDEX-fältets "BookmarkName"-egenskap.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// INDEX-fältet kommer att plocka upp denna post eftersom den är inuti bokmärket,
// och dess inmatningstyp matchar också INDEX-fältets inmatningstyp.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// Infoga ett XE-fält som inte kommer att visas i INDEX eftersom posttyperna inte matchar.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// Avsluta bokmärket och infoga ett XE-fält efteråt.
// Det är av samma typ som INDEX-fältet, men kommer inte att visas
// eftersom det är utanför bokmärkets gränser.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### Se även

* class [FieldXE](../)
* namnutrymme [Aspose.Words.Fields](../../fieldxe/)
* hopsättning [Aspose.Words](../../../)


