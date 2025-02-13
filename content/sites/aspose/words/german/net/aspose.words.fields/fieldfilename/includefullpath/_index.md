---
title: FieldFileName.IncludeFullPath
second_title: Aspose.Words für .NET-API-Referenz
description: FieldFileName eigendom. Ruft ab oder legt fest ob der vollständige Dateipfadname eingeschlossen werden soll.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldfilename/includefullpath/
---
## FieldFileName.IncludeFullPath property

Ruft ab oder legt fest, ob der vollständige Dateipfadname eingeschlossen werden soll.

```csharp
public bool IncludeFullPath { get; set; }
```

### Beispiele

Zeigt, wie FieldOptions verwendet wird, um den Standardwert für das Feld FILENAME zu überschreiben.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// Dieses FILENAME-Feld zeigt den Dateinamen des lokalen Systems des geladenen Dokuments an.
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// Standardmäßig zeigt das Feld FILENAME den Namen der Datei, aber nicht ihren vollständigen lokalen Dateisystempfad.
// Wir können ein Flag setzen, damit es den vollständigen Dateipfad anzeigt.
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// Wir können auch einen Wert für diese Eigenschaft setzen auf
// Wert überschreiben, der im Feld FILENAME angezeigt wird.
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### Siehe auch

* class [FieldFileName](../)
* namensraum [Aspose.Words.Fields](../../fieldfilename/)
* Montage [Aspose.Words](../../../)


