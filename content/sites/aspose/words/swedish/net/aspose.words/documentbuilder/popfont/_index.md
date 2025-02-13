---
title: DocumentBuilder.PopFont
second_title: Aspose.Words för .NET API Referens
description: DocumentBuilder metod. Hämtar teckenformatering som tidigare sparats i stacken.
type: docs
weight: 560
url: /sv/net/aspose.words/documentbuilder/popfont/
---
## DocumentBuilder.PopFont method

Hämtar teckenformatering som tidigare sparats i stacken.

```csharp
public void PopFont()
```

### Exempel

Visar hur du använder en dokumentbyggares formateringsstack.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ställ in teckensnittsformatering och skriv sedan texten som går före hyperlänken.
builder.Font.Name = "Arial";
builder.Font.Size = 24;
builder.Write("To visit Google, hold Ctrl and click ");

// Bevara vår nuvarande formateringskonfiguration i stacken.
builder.PushFont();

// Ändra byggarens nuvarande formatering genom att använda en ny stil.
builder.Font.StyleIdentifier = StyleIdentifier.Hyperlink;
builder.InsertHyperlink("here", "http://www.google.com", false);

Assert.AreEqual(Color.Blue.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.Single, builder.Font.Underline);

// Återställ teckensnittsformateringen som vi sparade tidigare och ta bort elementet från stacken.
builder.PopFont();

Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.None, builder.Font.Underline);

builder.Write(". We hope you enjoyed the example.");

doc.Save(ArtifactsDir + "DocumentBuilder.PushPopFont.docx");
```

### Se även

* property [Font](../font/)
* method [PushFont](../pushfont/)
* class [DocumentBuilder](../)
* namnutrymme [Aspose.Words](../../documentbuilder/)
* hopsättning [Aspose.Words](../../../)


