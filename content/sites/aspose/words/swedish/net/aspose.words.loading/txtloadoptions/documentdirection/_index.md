---
title: TxtLoadOptions.DocumentDirection
second_title: Aspose.Words för .NET API Referens
description: TxtLoadOptions fast egendom. Hämtar eller ställer in en dokumentriktning. Standardvärdet ärLeftToRight .
type: docs
weight: 30
url: /sv/net/aspose.words.loading/txtloadoptions/documentdirection/
---
## TxtLoadOptions.DocumentDirection property

Hämtar eller ställer in en dokumentriktning. Standardvärdet ärLeftToRight .

```csharp
public DocumentDirection DocumentDirection { get; set; }
```

### Exempel

Visar hur man upptäcker textriktning i klartextdokument.

```csharp
// Skapa ett "TxtLoadOptions"-objekt, som vi kan skicka till ett dokuments konstruktor
// för att ändra hur vi laddar ett dokument i klartext.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Ställ in egenskapen "DocumentDirection" till "DocumentDirection.Auto" upptäcker automatiskt
// riktningen för varje textstycke som Aspose.Words laddar från klartext.
// Varje styckes "Bidi"-egenskap kommer att lagra dess riktning.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// Upptäck hebreisk text som höger till vänster.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// Upptäck engelsk text som höger till vänster.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

### Se även

* enum [DocumentDirection](../../documentdirection/)
* class [TxtLoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../txtloadoptions/)
* hopsättning [Aspose.Words](../../../)


