---
title: SaveOptions.UpdateLastSavedTimeProperty
second_title: Aspose.Words för .NET API Referens
description: SaveOptions fast egendom. Hämtar eller ställer in ett värde som avgör omLastSavedTime egenskapen uppdateras innan du sparar.
type: docs
weight: 190
url: /sv/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/
---
## SaveOptions.UpdateLastSavedTimeProperty property

Hämtar eller ställer in ett värde som avgör om[`LastSavedTime`](../../../aspose.words.properties/builtindocumentproperties/lastsavedtime/) egenskapen uppdateras innan du sparar.

```csharp
public bool UpdateLastSavedTimeProperty { get; set; }
```

### Exempel

Visar hur du bestämmer om dokumentets "Sista sparade tid"-egenskap ska bevaras när du sparar.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
    doc.BuiltInDocumentProperties.LastSavedTime);

// När vi sparar dokumentet i ett OOXML-format kan vi skapa ett OoxmlSaveOptions-objekt
// och skicka det sedan till dokumentets sparmetod för att ändra hur vi sparar dokumentet.
// Ställ in egenskapen "UpdateLastSavedTimeProperty" till "true" till
// ställ in utdatadokumentets inbyggda egenskap "Senast sparad tid" till aktuellt datum/tid.
// Ställ in egenskapen "UpdateLastSavedTimeProperty" till "false" till
// bevara det ursprungliga värdet för indatadokumentets inbyggda egenskap "Sista sparade tid".
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.UpdateLastSavedTimeProperty = updateLastSavedTimeProperty;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx", saveOptions);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx");
DateTime lastSavedTimeNew = doc.BuiltInDocumentProperties.LastSavedTime;

if (updateLastSavedTimeProperty)
    Assert.That(DateTime.Now, Is.EqualTo(lastSavedTimeNew).Within(1).Days);
else
    Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
        lastSavedTimeNew);
```

### Se även

* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)


