---
title: BuiltInDocumentProperties.Thumbnail
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Ruft die Miniaturansicht des Dokuments ab oder legt diese fest.
type: docs
weight: 280
url: /de/net/aspose.words.properties/builtindocumentproperties/thumbnail/
---
## BuiltInDocumentProperties.Thumbnail property

Ruft die Miniaturansicht des Dokuments ab oder legt diese fest.

```csharp
public byte[] Thumbnail { get; set; }
```

### Bemerkungen

Derzeit wird diese Eigenschaft nur verwendet, wenn ein Dokument nach ePub exportiert wird, es wird nicht aus anderen Dokumentformaten gelesen und in diese geschrieben.

Bild eines beliebigen Formats kann auf diese Eigenschaft gesetzt werden, aber das Format wird während des Exports überprüft. InvalidOperationException wird ausgelöst, wenn das Bild ungültig ist oder sein Format für ein -spezifisches Format des Dokuments nicht unterstützt wird.

Für die ePub-Veröffentlichung können nur GIF-, JPEG- und PNG-Bilder verwendet werden.

### Beispiele

Zeigt, wie Sie einem Dokument, das wir als Epub speichern, eine Miniaturansicht hinzufügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Wenn wir ein Dokument, dessen "Thumbnail"-Eigenschaft Bilddaten enthält, die wir hinzugefügt haben, als Epub speichern,
// Ein Leser, der dieses Dokument öffnet, kann das Bild vor der ersten Seite anzeigen.
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

byte[] thumbnailBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");
properties.Thumbnail = thumbnailBytes;

doc.Save(ArtifactsDir + "DocumentProperties.Thumbnail.epub");

// Wir können das Miniaturbild eines Dokuments extrahieren und es im lokalen Dateisystem speichern.
DocumentProperty thumbnail = doc.BuiltInDocumentProperties["Thumbnail"];
File.WriteAllBytes(ArtifactsDir + "DocumentProperties.Thumbnail.gif", thumbnail.ToByteArray());
```

### Siehe auch

* class [BuiltInDocumentProperties](../)
* namensraum [Aspose.Words.Properties](../../builtindocumentproperties/)
* Montage [Aspose.Words](../../../)


