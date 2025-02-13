---
title: SaveOptions.UpdateLastSavedTimeProperty
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Ruft einen Wert ab oder legt ihn fest der bestimmt ob dieLastSavedTime Eigenschaft wird vor dem Speichern aktualisiert.
type: docs
weight: 190
url: /de/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/
---
## SaveOptions.UpdateLastSavedTimeProperty property

Ruft einen Wert ab oder legt ihn fest, der bestimmt, ob die[`LastSavedTime`](../../../aspose.words.properties/builtindocumentproperties/lastsavedtime/) Eigenschaft wird vor dem Speichern aktualisiert.

```csharp
public bool UpdateLastSavedTimeProperty { get; set; }
```

### Beispiele

Zeigt, wie Sie bestimmen, ob die Eigenschaft „Zuletzt gespeichert“ des Dokuments beim Speichern beibehalten werden soll.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
    doc.BuiltInDocumentProperties.LastSavedTime);

// Wenn wir das Dokument in einem OOXML-Format speichern, können wir ein OoxmlSaveOptions-Objekt erstellen
// und dann an die Speichermethode des Dokuments übergeben, um zu ändern, wie wir das Dokument speichern.
// Setzen Sie die Eigenschaft "UpdateLastSavedTimeProperty" auf "true".
// setze die eingebaute Eigenschaft "Letzte Speicherzeit" des Ausgabedokuments auf das aktuelle Datum/die aktuelle Uhrzeit.
// Setzen Sie die Eigenschaft "UpdateLastSavedTimeProperty" auf "false".
// Originalwert der eingebauten Eigenschaft "Zuletzt gespeichert" des Eingabedokuments beibehalten.
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

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


