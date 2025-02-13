---
title: SaveOptions.UpdateLastSavedTimeProperty
second_title: Aspose.Words per .NET API Reference
description: SaveOptions proprietà. Ottiene o imposta un valore che determina se ilLastSavedTime la proprietà viene aggiornata prima del salvataggio.
type: docs
weight: 190
url: /it/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/
---
## SaveOptions.UpdateLastSavedTimeProperty property

Ottiene o imposta un valore che determina se il[`LastSavedTime`](../../../aspose.words.properties/builtindocumentproperties/lastsavedtime/) la proprietà viene aggiornata prima del salvataggio.

```csharp
public bool UpdateLastSavedTimeProperty { get; set; }
```

### Esempi

Mostra come determinare se mantenere la proprietà "Ultima ora salvata" del documento durante il salvataggio.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
    doc.BuiltInDocumentProperties.LastSavedTime);

// Quando salviamo il documento in un formato OOXML, possiamo creare un oggetto OoxmlSaveOptions
// e quindi passalo al metodo di salvataggio del documento per modificare il modo in cui salviamo il documento.
// Imposta la proprietà "UpdateLastSavedTimeProperty" su "true" su
// imposta la proprietà incorporata "Ultima ora salvata" del documento di output sulla data/ora corrente.
// Imposta la proprietà "UpdateLastSavedTimeProperty" su "false" su
// conserva il valore originale della proprietà incorporata "Ultima ora salvata" del documento di input.
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

### Guarda anche

* class [SaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../saveoptions/)
* assemblea [Aspose.Words](../../../)


