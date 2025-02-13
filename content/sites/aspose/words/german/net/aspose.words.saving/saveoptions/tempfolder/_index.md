---
title: SaveOptions.TempFolder
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Gibt den Ordner für temporäre Dateien an der beim Speichern in eine DOC oder DOCXDatei verwendet wird. Standardmäßig ist diese EigenschaftNull und es werden keine temporären Dateien verwendet.
type: docs
weight: 150
url: /de/net/aspose.words.saving/saveoptions/tempfolder/
---
## SaveOptions.TempFolder property

Gibt den Ordner für temporäre Dateien an, der beim Speichern in eine DOC- oder DOCX-Datei verwendet wird. Standardmäßig ist diese Eigenschaft`Null` und es werden keine temporären Dateien verwendet.

```csharp
public string TempFolder { get; set; }
```

### Bemerkungen

Wenn Aspose.Words ein Dokument speichert, muss es temporäre interne Strukturen erstellen. Standardmäßig werden diese internen Strukturen im Speicher erstellt und die Speicherauslastung steigt kurzzeitig an, während das Dokument gespeichert wird. Wenn das Speichern abgeschlossen ist, wird der Speicher freigegeben und vom Garbage Collector zurückgefordert.

Wenn Sie ein sehr großes Dokument (Tausende von Seiten) speichern und/oder viele Dokumente gleichzeitig verarbeiten, , dann kann die Speicherspitze während des Speicherns so groß sein, dass das System abstürztOutOfMemoryException . Festlegen eines temporären Ordners mit`TempFolder` bewirkt, dass Aspose.Words die internen Strukturen in temporären Dateien statt im Speicher behält. Es reduziert die Speichernutzung während des Speicherns, verringert jedoch die Speicherleistung.

Der Ordner muss vorhanden und beschreibbar sein, andernfalls wird eine Ausnahme ausgelöst.

Aspose.Words löscht automatisch alle temporären Dateien, wenn das Speichern abgeschlossen ist.

### Beispiele

Zeigt, wie beim Speichern eines Dokuments die Festplatte anstelle des Arbeitsspeichers verwendet wird.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Wenn wir ein Dokument speichern, werden verschiedene Elemente vorübergehend im Speicher gespeichert, während der Speichervorgang stattfindet.
// Wir können diese Option verwenden, um stattdessen einen temporären Ordner im lokalen Dateisystem zu verwenden,
// was den Speicheraufwand unserer Anwendung reduziert.
DocSaveOptions options = new DocSaveOptions();
options.TempFolder = ArtifactsDir + "TempFiles";

// Der angegebene temporäre Ordner muss vor dem Speichervorgang im lokalen Dateisystem vorhanden sein.
Directory.CreateDirectory(options.TempFolder);

doc.Save(ArtifactsDir + "DocSaveOptions.TempFolder.doc", options);

// Der Ordner wird ohne Restinhalte aus dem Ladevorgang bestehen bleiben.
Assert.That(Directory.GetFiles(options.TempFolder), Is.Empty);
```

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


