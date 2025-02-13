---
title: DocumentBuilder.Underline
second_title: Aspose.Words för .NET API Referens
description: DocumentBuilder fast egendom. Hämtar/ställer in understrykningstyp för det aktuella teckensnittet.
type: docs
weight: 170
url: /sv/net/aspose.words/documentbuilder/underline/
---
## DocumentBuilder.Underline property

Hämtar/ställer in understrykningstyp för det aktuella teckensnittet.

```csharp
public Underline Underline { get; set; }
```

### Exempel

Visar hur man formaterar text som infogats av en dokumentbyggare.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Underline = Underline.Dash;
builder.Font.Color = Color.Blue;
builder.Font.Size = 32;

// Byggaren tillämpar formatering på sitt nuvarande stycke och all ny text som lagts till efteråt.
builder.Writeln("Large, blue, and underlined text.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertUnderline.docx");
```

### Se även

* enum [Underline](../../underline/)
* class [DocumentBuilder](../)
* namnutrymme [Aspose.Words](../../documentbuilder/)
* hopsättning [Aspose.Words](../../../)


