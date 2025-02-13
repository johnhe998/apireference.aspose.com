---
title: SaveOptions.UpdateLastPrintedProperty
second_title: Aspose.Words för .NET API Referens
description: SaveOptions fast egendom. Hämtar eller ställer in ett värde som avgör omLastPrinted egenskapen uppdateras innan du sparar.
type: docs
weight: 180
url: /sv/net/aspose.words.saving/saveoptions/updatelastprintedproperty/
---
## SaveOptions.UpdateLastPrintedProperty property

Hämtar eller ställer in ett värde som avgör om[`LastPrinted`](../../../aspose.words.properties/builtindocumentproperties/lastprinted/) egenskapen uppdateras innan du sparar.

```csharp
public bool UpdateLastPrintedProperty { get; set; }
```

### Exempel

Visar hur du uppdaterar ett dokuments "CreatedTime"-egenskap när du sparar.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.CreatedTime = new DateTime(2019, 12, 20);

// Denna flagga avgör om den skapade tiden, som är en inbyggd egenskap, uppdateras.
// Om så är fallet, då datumet för dokumentets senaste lagringsåtgärd
// med detta SaveOptions-objekt som skickas som en parameter används som skapad tid.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateCreatedTimeProperty = isUpdateCreatedTimeProperty;

doc.Save(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx", saveOptions);

// Öppna det sparade dokumentet och verifiera sedan värdet på egenskapen.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx");

Assert.AreNotEqual(isUpdateCreatedTimeProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.CreatedTime);
```

Visar hur du uppdaterar ett dokuments "Senast utskrivna"-egenskap när du sparar.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.LastPrinted = new DateTime(2019, 12, 20);

// Denna flagga avgör om det senast utskrivna datumet, som är en inbyggd egenskap, uppdateras.
// Om så är fallet, då datumet för dokumentets senaste lagringsåtgärd
// med detta SaveOptions-objekt som skickas som en parameter används som utskriftsdatum.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateLastPrintedProperty = isUpdateLastPrintedProperty;

// I Microsoft Word 2003 kan den här egenskapen hittas via Arkiv -> Egenskaper -> Statistik -> Tryckt.
// Det kan också visas i dokumentets brödtext genom att använda ett PRINTDATE-fält.
doc.Save(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc", saveOptions);

// Öppna det sparade dokumentet och verifiera sedan värdet på egenskapen.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc");

Assert.AreNotEqual(isUpdateLastPrintedProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.LastPrinted);
```

### Se även

* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)


