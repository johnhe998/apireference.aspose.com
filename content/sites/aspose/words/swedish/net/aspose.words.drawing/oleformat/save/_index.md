---
title: OleFormat.Save
second_title: Aspose.Words för .NET API Referens
description: OleFormat metod. Sparar data för det inbäddade objektet i den angivna strömmen.
type: docs
weight: 160
url: /sv/net/aspose.words.drawing/oleformat/save/
---
## Save(Stream) {#save}

Sparar data för det inbäddade objektet i den angivna strömmen.

```csharp
public void Save(Stream stream)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| stream | Stream | Var ska objektdata sparas. |

### Undantag

| undantag | skick |
| --- | --- |
| InvalidOperationException | Kastar om du försöker spara ett länkat objekt. |

### Anmärkningar

Det är uppringarens ansvar att göra sig av med strömmen.

### Exempel

Visar hur man extraherar inbäddade OLE-objekt till filer.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// OLE-objektet i den första formen är ett Microsoft Excel-kalkylblad.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Vårt objekt är varken automatisk uppdatering eller låst från uppdateringar.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// Om vi planerar att spara OLE-objektet till en fil i det lokala filsystemet,
// vi kan använda egenskapen "SuggestedExtension" för att avgöra vilket filtillägg som ska tillämpas på filen.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// Nedan finns två sätt att spara ett OLE-objekt till en fil i det lokala filsystemet.
// 1 - Spara den via en stream:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Spara det direkt till ett filnamn:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Se även

* class [OleFormat](../)
* namnutrymme [Aspose.Words.Drawing](../../oleformat/)
* hopsättning [Aspose.Words](../../../)

---

## Save(string) {#save_1}

Sparar data för det inbäddade objektet i en fil med det angivna namnet.

```csharp
public void Save(string fileName)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fileName | String | Namn på filen för att spara OLE-objektdata. |

### Undantag

| undantag | skick |
| --- | --- |
| InvalidOperationException | Kastar om du försöker spara ett länkat objekt. |

### Exempel

Visar hur man extraherar inbäddade OLE-objekt till filer.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// OLE-objektet i den första formen är ett Microsoft Excel-kalkylblad.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Vårt objekt är varken automatisk uppdatering eller låst från uppdateringar.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// Om vi planerar att spara OLE-objektet till en fil i det lokala filsystemet,
// vi kan använda egenskapen "SuggestedExtension" för att avgöra vilket filtillägg som ska tillämpas på filen.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// Nedan finns två sätt att spara ett OLE-objekt till en fil i det lokala filsystemet.
// 1 - Spara den via en stream:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Spara det direkt till ett filnamn:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Se även

* class [OleFormat](../)
* namnutrymme [Aspose.Words.Drawing](../../oleformat/)
* hopsättning [Aspose.Words](../../../)


