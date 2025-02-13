---
title: CustomXmlPart.DataChecksum
second_title: Aspose.Words per .NET API Reference
description: CustomXmlPart proprietà. Specifica un checksum CRC Cyclic Redundancy Check delData contenuto.
type: docs
weight: 30
url: /it/net/aspose.words.markup/customxmlpart/datachecksum/
---
## CustomXmlPart.DataChecksum property

Specifica un checksum CRC (Cyclic Redundancy Check) del[`Data`](../data/) contenuto.

```csharp
public long DataChecksum { get; }
```

### Esempi

Mostra come viene calcolato il checksum in un runtime.

```csharp
Document doc = new Document();

StructuredDocumentTag richText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(richText);

// Il checksum è di sola lettura e viene calcolato utilizzando i dati della parte di dati XML personalizzata corrispondente.
richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>ContentControl</text></root>"), "/root/text", "");

long checksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(checksum);

richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>Updated ContentControl</text></root>"), "/root/text", "");

long updatedChecksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(updatedChecksum);

// Abbiamo modificato l'XmlPart del tag e il checksum è stato aggiornato in fase di esecuzione.
Assert.AreNotEqual(checksum, updatedChecksum);
```

### Guarda anche

* class [CustomXmlPart](../)
* spazio dei nomi [Aspose.Words.Markup](../../customxmlpart/)
* assemblea [Aspose.Words](../../../)


