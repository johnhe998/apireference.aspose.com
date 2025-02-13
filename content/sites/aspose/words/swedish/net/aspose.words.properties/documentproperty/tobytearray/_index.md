---
title: DocumentProperty.ToByteArray
second_title: Aspose.Words för .NET API Referens
description: DocumentProperty metod. Returnerar egenskapsvärdet som byte array.
type: docs
weight: 70
url: /sv/net/aspose.words.properties/documentproperty/tobytearray/
---
## DocumentProperty.ToByteArray method

Returnerar egenskapsvärdet som byte array.

```csharp
public byte[] ToByteArray()
```

### Anmärkningar

Kastar ett undantag om egenskapstypen inte är detByteArray.

### Exempel

Visar hur man lägger till en miniatyrbild till ett dokument som vi sparar som en Epub.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Om vi sparar ett dokument, vars "Thumbnail"-egenskap innehåller bilddata som vi har lagt till, som en Epub,
// en läsare som öppnar det dokumentet kan visa bilden före den första sidan.
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

byte[] thumbnailBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");
properties.Thumbnail = thumbnailBytes;

doc.Save(ArtifactsDir + "DocumentProperties.Thumbnail.epub");

// Vi kan extrahera ett dokuments miniatyrbild och spara den i det lokala filsystemet.
DocumentProperty thumbnail = doc.BuiltInDocumentProperties["Thumbnail"];
File.WriteAllBytes(ArtifactsDir + "DocumentProperties.Thumbnail.gif", thumbnail.ToByteArray());
```

### Se även

* class [DocumentProperty](../)
* namnutrymme [Aspose.Words.Properties](../../documentproperty/)
* hopsättning [Aspose.Words](../../../)


