---
title: SaveOptions.DefaultTemplate
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Ruft den Pfad zur Standardvorlage einschließlich Dateiname ab oder legt ihn fest. Der Standardwert für diese Eigenschaft ist leerer String Empty .
type: docs
weight: 40
url: /de/net/aspose.words.saving/saveoptions/defaulttemplate/
---
## SaveOptions.DefaultTemplate property

Ruft den Pfad zur Standardvorlage (einschließlich Dateiname) ab oder legt ihn fest. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ).

```csharp
public string DefaultTemplate { get; set; }
```

### Bemerkungen

Wenn angegeben, wird dieser Pfad verwendet, um die Vorlage wann zu laden[`AutomaticallyUpdateStyles`](../../../aspose.words/document/automaticallyupdatestyles/) ist wahr, aber[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) ist leer.

### Beispiele

Zeigt, wie Sie eine Standardvorlage für Dokumente festlegen, die keine angehängten Vorlagen haben.

```csharp
Document doc = new Document();

// Automatische Stilaktualisierung aktivieren, aber kein Vorlagendokument anhängen.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Da es kein Vorlagendokument gibt, konnte das Dokument Stiländerungen nirgendwo nachverfolgen.
// Verwenden Sie ein SaveOptions-Objekt, um automatisch eine Vorlage festzulegen
// wenn ein Dokument, das wir speichern, keines hat.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


