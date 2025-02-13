---
title: DocumentProperty.ToByteArray
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentProperty methode. Gibt den Eigenschaftswert als ByteArray zurück.
type: docs
weight: 70
url: /de/net/aspose.words.properties/documentproperty/tobytearray/
---
## DocumentProperty.ToByteArray method

Gibt den Eigenschaftswert als Byte-Array zurück.

```csharp
public byte[] ToByteArray()
```

### Bemerkungen

Löst eine Ausnahme aus, wenn der Eigenschaftstyp nicht istByteArray.

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

* class [DocumentProperty](../)
* namensraum [Aspose.Words.Properties](../../documentproperty/)
* Montage [Aspose.Words](../../../)


