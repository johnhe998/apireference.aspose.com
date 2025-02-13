---
title: FieldSeq.BookmarkName
second_title: Aspose.Words för .NET API Referens
description: FieldSeq fast egendom. Hämtar eller ställer in ett bokmärkesnamn som refererar till ett objekt någon annanstans i dokumentet snarare än på den aktuella platsen.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldseq/bookmarkname/
---
## FieldSeq.BookmarkName property

Hämtar eller ställer in ett bokmärkesnamn som refererar till ett objekt någon annanstans i dokumentet snarare än på den aktuella platsen.

```csharp
public string BookmarkName { get; set; }
```

### Exempel

Visar hur man kombinerar innehållsförteckning och sekvensfält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ett TOC-fält kan skapa en post i dess innehållsförteckning för varje SEQ-fält som finns i dokumentet.
// Varje post innehåller stycket som innehåller SEQ-fältet,
// och numret på sidan som fältet visas på.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// Konfigurera detta TOC-fält så att det har en SequenceIdentifier-egenskap med värdet "MySequence".
fieldToc.TableOfFiguresLabel = "MySequence";

// Konfigurera detta innehållsförteckningsfält för att bara ta upp SEQ-fält som ligger inom gränserna för ett bokmärke
// heter "TOCBookmark".
fieldToc.BookmarkName = "TOCBookmark";
builder.InsertBreak(BreakType.PageBreak);

Assert.AreEqual(" TOC  \\c MySequence \\b TOCBookmark", fieldToc.GetFieldCode());

// SEQ-fält visar ett antal som ökar vid varje SEQ-fält.
// Dessa fält har också separata räkningar för varje unik namngiven sekvens
// identifieras av SEQ-fältets "SequenceIdentifier"-egenskap.
// Infoga ett SEQ-fält som har en sekvensidentifierare som matchar innehållsförteckningarna
// TableOfFiguresLabel-egenskap. Detta fält kommer inte att skapa en post i innehållsförteckningen eftersom det är utanför
// bokmärkets gränser angivna av "BookmarkName".
builder.Write("MySequence #");
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", will not show up in the TOC because it is outside of the bookmark.");

builder.StartBookmark("TOCBookmark");

// Detta SEQ-fälts sekvens matchar innehållsförteckningens "TableOfFiguresLabel"-egenskap och är inom bokmärkets gränser.
// Stycket som innehåller detta fält kommer att visas i innehållsförteckningen som en post.
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", will show up in the TOC next to the entry for the above caption.");

// Detta SEQ-fälts sekvens matchar inte innehållsförteckningens "TableOfFiguresLabel"-egenskap,
// och är inom gränserna för bokmärket. Dess stycke kommer inte att visas i innehållsförteckningen som en post.
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "OtherSequence";
builder.Writeln(", will not show up in the TOC because it's from a different sequence identifier.");

// Detta SEQ-fälts sekvens matchar innehållsförteckningens "TableOfFiguresLabel"-egenskap och är inom bokmärkets gränser.
// Detta fält refererar också till ett annat bokmärke. Innehållet i det bokmärket kommer att visas i TOC-posten för detta SEQ-fält.
// Själva SEQ-fältet visar inte innehållet i det bokmärket.
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.BookmarkName = "SEQBookmark";
Assert.AreEqual(" SEQ  MySequence SEQBookmark", fieldSeq.GetFieldCode());

// Skapa ett bokmärke med innehåll som kommer att dyka upp i TOC-posten på grund av att ovanstående SEQ-fält refererar till det.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("SEQBookmark");
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", text from inside SEQBookmark.");
builder.EndBookmark("SEQBookmark");

builder.EndBookmark("TOCBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SEQ.Bookmark.docx");
```

### Se även

* class [FieldSeq](../)
* namnutrymme [Aspose.Words.Fields](../../fieldseq/)
* hopsättning [Aspose.Words](../../../)


