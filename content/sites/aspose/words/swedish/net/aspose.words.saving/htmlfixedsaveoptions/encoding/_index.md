---
title: HtmlFixedSaveOptions.Encoding
second_title: Aspose.Words för .NET API Referens
description: HtmlFixedSaveOptions fast egendom. Anger kodningen som ska användas vid export till HTML. Standardvärdet ärny UTF8Encodingtrue UTF8 med BOM.
type: docs
weight: 30
url: /sv/net/aspose.words.saving/htmlfixedsaveoptions/encoding/
---
## HtmlFixedSaveOptions.Encoding property

Anger kodningen som ska användas vid export till HTML. Standardvärdet är`ny UTF8Encoding(true)` (UTF-8 med BOM).

```csharp
public Encoding Encoding { get; set; }
```

### Exempel

Visar hur du ställer in vilken kodning som ska användas när ett dokument exporteras till HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello World!");

// Standardkodningen är UTF-8. Om vi vill representera vårt dokument med en annan kodning,
// vi kan använda ett SaveOptions-objekt för att ställa in en specifik kodning.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    Encoding = Encoding.GetEncoding("ASCII")
};

Assert.AreEqual("US-ASCII", htmlFixedSaveOptions.Encoding.EncodingName);

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UseEncoding.html", htmlFixedSaveOptions);
```

### Se även

* class [HtmlFixedSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* hopsättning [Aspose.Words](../../../)


