---
title: Font.AutoColor
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Returnerar den aktuella beräknade färgen på texten svart eller vit som ska användas för autofärg. Om färgen inte är auto returnerasColor .
type: docs
weight: 20
url: /sv/net/aspose.words/font/autocolor/
---
## Font.AutoColor property

Returnerar den aktuella beräknade färgen på texten (svart eller vit) som ska användas för 'autofärg'. Om färgen inte är 'auto' returneras[`Color`](../color/) .

```csharp
public Color AutoColor { get; }
```

### Anmärkningar

När text har 'automatisk färg', beräknas den faktiska färgen på text automatiskt så att den är läsbar mot bakgrundsfärgen. När du ändrar bakgrundsfärgen, kommer textfärgen automatiskt att växla till svart eller vit i MS Word för att maximera läsbarheten.

### Exempel

Visar hur man förbättrar läsbarheten genom att automatiskt välja textfärg baserat på bakgrundens ljusstyrka.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Om en körs Font-objekt inte anger textfärg kommer det automatiskt
// välj antingen svart eller vit beroende på bakgrundsfärgens färg.
Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());

// Standardfärgen för text är svart. Om färgen på bakgrunden är mörk blir svart text svår att se.
// För att lösa detta problem kommer AutoColor-egenskapen att visa denna text i vitt.
builder.Font.Shading.BackgroundPatternColor = Color.DarkBlue;

builder.Writeln("The text color automatically chosen for this run is white.");

Assert.AreEqual(Color.White.ToArgb(), doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.AutoColor.ToArgb());

// Om vi ändrar bakgrunden till en ljus färg blir svart en mer
// lämplig textfärg än vit så att autofärgen kommer att visa den i svart.
builder.Font.Shading.BackgroundPatternColor = Color.LightBlue;

builder.Writeln("The text color automatically chosen for this run is black.");

Assert.AreEqual(Color.Black.ToArgb(), doc.FirstSection.Body.Paragraphs[1].Runs[0].Font.AutoColor.ToArgb());

doc.Save(ArtifactsDir + "Font.SetFontAutoColor.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


