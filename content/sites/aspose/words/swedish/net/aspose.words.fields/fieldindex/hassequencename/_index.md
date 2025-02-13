---
title: FieldIndex.HasSequenceName
second_title: Aspose.Words för .NET API Referens
description: FieldIndex fast egendom. Får ett värde som indikerar om en sekvens ska användas medan fältets resultat byggs.
type: docs
weight: 60
url: /sv/net/aspose.words.fields/fieldindex/hassequencename/
---
## FieldIndex.HasSequenceName property

Får ett värde som indikerar om en sekvens ska användas medan fältets resultat byggs.

```csharp
public bool HasSequenceName { get; }
```

### Exempel

Visar hur man delar upp ett dokument i delar genom att kombinera INDEX- och SEQ-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa ett INDEX-fält som visar en post för varje XE-fält som finns i dokumentet.
// Varje post kommer att visa XE-fältets textegenskapsvärde på vänster sida,
// och numret på sidan som innehåller XE-fältet till höger.
// Om XE-fälten har samma värde i egenskapen "Text",
// INDEX-fältet grupperar dem i en post.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Namnge en SEQ-fältsekvens i egenskapen SequenceName. Varje post i detta INDEX-fält kommer nu också att visas
// numret som sekvensräkningen är på vid XE-fältplatsen som skapade denna post.
index.SequenceName = "MySequence";

// Ställ in text som kommer runt sekvensen och sidnumren för att förklara deras betydelse för användaren.
// En post som skapats med denna konfiguration kommer att visa något i stil med "MySequence at 1 on page 1" vid dess sidnummer.
// PageNumberSeparator och SequenceSeparator får inte vara längre än 15 tecken.
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// SEQ-fält visar ett antal som ökar vid varje SEQ-fält.
// Dessa fält har också separata räkningar för varje unik namngiven sekvens
// identifieras av SEQ-fältets "SequenceIdentifier"-egenskap.
// Infoga ett SEQ-fält som flyttar "MySequence"-sekvensen till 1.
// Detta fält skiljer sig inte från normal dokumenttext. Det kommer inte att visas i ett INDEX-fälts innehållsförteckning.
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// Infoga ett XE-fält som skapar en post i INDEX-fältet.
// Eftersom "MySequence" är på 1 och detta XE-fält finns på sidan 2, tillsammans med de anpassade separatorer vi definierade ovan,
// Detta fälts INDEX-post kommer att visa "Cat" på vänster sida och "MySequence at 1 on page 2" till höger.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// Infoga en sidbrytning och använd SEQ-fält för att flytta "MySequence" till 3.
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// Infoga ett XE-fält med samma Text-egenskap som ovan.
// INDEX-posten kommer att gruppera XE-fält med matchande värden i egenskapen "Text"
// i en post i motsats till att göra en post för varje XE-fält.
// Eftersom vi är på sidan 2 med "MySequence" vid 3, kommer ", 3 på sidan 3" att läggas till samma INDEX-post som ovan.
// Sidnummerdelen av den INDEX-posten kommer nu att visa "MySequence at 1 on page 2, 3 on page 3".
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// Infoga ett XE-fält med ett nytt och unikt textegenskapsvärde.
// Detta kommer att lägga till en ny post, med MySequence vid 3 på sidan 4.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### Se även

* class [FieldIndex](../)
* namnutrymme [Aspose.Words.Fields](../../fieldindex/)
* hopsättning [Aspose.Words](../../../)


