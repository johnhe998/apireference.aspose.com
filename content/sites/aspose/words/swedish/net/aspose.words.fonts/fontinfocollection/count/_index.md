---
title: FontInfoCollection.Count
second_title: Aspose.Words för .NET API Referens
description: FontInfoCollection fast egendom. Hämtar antalet element som finns i samlingen.
type: docs
weight: 10
url: /sv/net/aspose.words.fonts/fontinfocollection/count/
---
## FontInfoCollection.Count property

Hämtar antalet element som finns i samlingen.

```csharp
public int Count { get; }
```

### Exempel

Visar information om de typsnitt som finns i det tomma dokumentet.

```csharp
Document doc = new Document();

// Ett tomt dokument innehåller 3 standardteckensnitt. Varje typsnitt i dokumentet
// kommer att ha ett motsvarande FontInfo-objekt som innehåller detaljer om det typsnittet.
Assert.AreEqual(3, doc.FontInfos.Count);

Assert.True(doc.FontInfos.Contains("Times New Roman"));
Assert.AreEqual(204, doc.FontInfos["Times New Roman"].Charset);

Assert.True(doc.FontInfos.Contains("Symbol"));
Assert.True(doc.FontInfos.Contains("Arial"));
```

### Se även

* class [FontInfoCollection](../)
* namnutrymme [Aspose.Words.Fonts](../../fontinfocollection/)
* hopsättning [Aspose.Words](../../../)


