---
title: FieldAutoNum.SeparatorCharacter
second_title: Aspose.Words för .NET API Referens
description: FieldAutoNum fast egendom. Hämtar eller ställer in avgränsningstecknet som ska användas.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldautonum/separatorcharacter/
---
## FieldAutoNum.SeparatorCharacter property

Hämtar eller ställer in avgränsningstecknet som ska användas.

```csharp
public string SeparatorCharacter { get; set; }
```

### Exempel

Visar hur man numrerar stycken med autonumeriska fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Varje AUTONUM-fält visar det aktuella värdet av ett löpande antal AUTONUM-fält,
// tillåter oss att automatiskt numrera objekt som en numrerad lista.
// Detta fält kommer att visa siffran "1.".
FieldAutoNum field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 1.");

Assert.AreEqual(" AUTONUM ", field.GetFieldCode());

field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 2.");

// Skiljetecknet, som visas i fältresultatet omedelbart efter numret, är som standard ett punkt.
// Om vi lämnar den här egenskapen null, kommer vårt andra AUTONUM-fält att visa "2." i dokumentet.
Assert.IsNull(field.SeparatorCharacter);

// Vi kan ställa in den här egenskapen för att tillämpa det första tecknet i dess sträng som det nya separatortecknet.
// I detta fall kommer vårt AUTONUM-fält nu att visa "2:".
field.SeparatorCharacter = ":";

Assert.AreEqual(" AUTONUM  \\s :", field.GetFieldCode());

doc.Save(ArtifactsDir + "Field.AUTONUM.docx");
```

### Se även

* class [FieldAutoNum](../)
* namnutrymme [Aspose.Words.Fields](../../fieldautonum/)
* hopsättning [Aspose.Words](../../../)


