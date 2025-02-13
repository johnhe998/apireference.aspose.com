---
title: FieldShape.Text
second_title: Aspose.Words för .NET API Referens
description: FieldShape fast egendom. Hämtar eller ställer in texten som ska hämtas.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldshape/text/
---
## FieldShape.Text property

Hämtar eller ställer in texten som ska hämtas.

```csharp
public string Text { get; set; }
```

### Exempel

Visar hur man skapar höger-till-vänster språkkompatibla listor med BIDIOUTLINE-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// BIDIOUTLINE-fältet numrerar stycken som AUTONUM/LISTNUM-fälten,
// men är bara synlig när ett redigeringsspråk från höger till vänster är aktiverat, till exempel hebreiska eller arabiska.
// Följande fält kommer att visa ".1", RTL-motsvarigheten till listnummer "1.".
FieldBidiOutline field = (FieldBidiOutline)builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

Assert.AreEqual(" BIDIOUTLINE ", field.GetFieldCode());

// Lägg till ytterligare två BIDIOUTLINE-fält, som kommer att visa ".2" och ".3".
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

// Ställ in den horisontella textjusteringen för varje stycke i dokumentet till RTL.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.Bidi = true;
}

// Om vi aktiverar ett redigeringsspråk från höger till vänster i Microsoft Word kommer våra fält att visa siffror.
// Annars kommer de att visa "###".
doc.Save(ArtifactsDir + "Field.BIDIOUTLINE.docx");
```

Visar hur vissa äldre Microsoft Word-fält som SHAPE och EMBED hanteras under laddning.

```csharp
// Öppna ett dokument som skapades i Microsoft Word 2003.
Document doc = new Document(MyDir + "Legacy fields.doc");

// Om vi öppnar Word-dokumentet och trycker på Alt+F9 kommer vi att se ett SHAPE- och ett EMBED-fält.
// Ett SHAPE-fält är ankare/canvas för ett AutoShape-objekt med inslagsstilen "I linje med text" aktiverad.
// Ett EMBED-fält har samma funktion, men för ett inbäddat objekt,
// som ett kalkylblad från ett externt Excel-dokument.
// Dessa fält kommer dock inte att visas i dokumentets fältsamling.
Assert.AreEqual(0, doc.Range.Fields.Count);

// Dessa fält stöds endast av gamla versioner av Microsoft Word.
// Dokumentladdningsprocessen kommer att konvertera dessa fält till Shape-objekt,
// som vi kan komma åt i dokumentets nodsamling.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);
Assert.AreEqual(3, shapes.Count);

// Den första Shape-noden motsvarar fältet SHAPE i inmatningsdokumentet,
// som är inline-duken för AutoShape.
Shape shape = (Shape)shapes[0];
Assert.AreEqual(ShapeType.Image, shape.ShapeType);

// Den andra Shape-noden är själva AutoShape.
shape = (Shape)shapes[1];
Assert.AreEqual(ShapeType.Can, shape.ShapeType);

// Den tredje Shape är det som var EMBED-fältet som innehöll det externa kalkylarket.
shape = (Shape)shapes[2];
Assert.AreEqual(ShapeType.OleObject, shape.ShapeType);
```

### Se även

* class [FieldShape](../)
* namnutrymme [Aspose.Words.Fields](../../fieldshape/)
* hopsättning [Aspose.Words](../../../)


