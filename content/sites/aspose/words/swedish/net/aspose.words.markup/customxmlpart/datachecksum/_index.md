---
title: CustomXmlPart.DataChecksum
second_title: Aspose.Words för .NET API Referens
description: CustomXmlPart fast egendom. Anger en cyklisk redundanskontroll CRC checksumma förData innehåll.
type: docs
weight: 30
url: /sv/net/aspose.words.markup/customxmlpart/datachecksum/
---
## CustomXmlPart.DataChecksum property

Anger en cyklisk redundanskontroll (CRC) checksumma för[`Data`](../data/) innehåll.

```csharp
public long DataChecksum { get; }
```

### Exempel

Visar hur kontrollsumman beräknas under en körning.

```csharp
Document doc = new Document();

StructuredDocumentTag richText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(richText);

// Kontrollsumman är skrivskyddad och beräknas med hjälp av data från motsvarande anpassade XML-datadel.
richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>ContentControl</text></root>"), "/root/text", "");

long checksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(checksum);

richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>Updated ContentControl</text></root>"), "/root/text", "");

long updatedChecksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(updatedChecksum);

// Vi ändrade XmlPart av taggen, och kontrollsumman uppdaterades vid körning.
Assert.AreNotEqual(checksum, updatedChecksum);
```

### Se även

* class [CustomXmlPart](../)
* namnutrymme [Aspose.Words.Markup](../../customxmlpart/)
* hopsättning [Aspose.Words](../../../)


