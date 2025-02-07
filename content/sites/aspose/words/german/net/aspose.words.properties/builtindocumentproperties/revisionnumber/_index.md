---
title: BuiltInDocumentProperties.RevisionNumber
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Ruft die Revisionsnummer des Dokuments ab oder legt sie fest.
type: docs
weight: 240
url: /de/net/aspose.words.properties/builtindocumentproperties/revisionnumber/
---
## BuiltInDocumentProperties.RevisionNumber property

Ruft die Revisionsnummer des Dokuments ab oder legt sie fest.

```csharp
public int RevisionNumber { get; set; }
```

### Bemerkungen

Aspose.Words aktualisiert diese Eigenschaft nicht.

### Beispiele

Zeigt, wie mit REVNUM-Feldern gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Current revision #");

// Ein REVNUM-Feld einfügen, das die Eigenschaft der aktuellen Revisionsnummer des Dokuments anzeigt.
FieldRevNum field = (FieldRevNum)builder.InsertField(FieldType.FieldRevisionNum, true);

Assert.AreEqual(" REVNUM ", field.GetFieldCode());
Assert.AreEqual("1", field.Result);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.RevisionNumber);

// Diese Eigenschaft zählt, wie oft ein Dokument in Microsoft Word gespeichert wurde,
// und hat nichts mit nachverfolgten Revisionen zu tun. Wir können es finden, indem wir im Windows Explorer mit der rechten Maustaste auf das Dokument klicken
// über Eigenschaften -> Einzelheiten. Wir können diese Eigenschaft manuell aktualisieren.
doc.BuiltInDocumentProperties.RevisionNumber++;

Assert.AreEqual("2", field.Result);
```

Zeigt, wie Sie mit Dokumenteigenschaften in der Kategorie "Ursprung" arbeiten.

```csharp
// Öffnen Sie ein Dokument, das wir mit Microsoft Word erstellt und bearbeitet haben.
Document doc = new Document(MyDir + "Properties.docx");
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// Die folgenden integrierten Eigenschaften enthalten Informationen zur Erstellung und Bearbeitung dieses Dokuments.
// Wir können dieses Dokument im Windows Explorer mit der rechten Maustaste anklicken und finden
// diese Eigenschaften über "Eigenschaften" -> "Details" -> Kategorie "Herkunft".
// Felder wie PRINTDATE und EDITTIME können diese Werte im Dokumentkörper anzeigen.
Console.WriteLine($"Created using {properties.NameOfApplication}, on {properties.CreatedTime}");
Console.WriteLine($"Minutes spent editing: {properties.TotalEditingTime}");
Console.WriteLine($"Date/time last printed: {properties.LastPrinted}");
Console.WriteLine($"Template document: {properties.Template}");

// Wir können auch die Werte von eingebauten Eigenschaften ändern.
properties.Company = "Doe Ltd.";
properties.Manager = "Jane Doe";
properties.Version = 5;
properties.RevisionNumber++;

// Microsoft Word aktualisiert die folgenden Eigenschaften automatisch, wenn wir das Dokument speichern.
// Um diese Eigenschaften mit Aspose.Words zu verwenden, müssen wir Werte für sie manuell festlegen.
properties.LastSavedBy = "John Doe";
properties.LastSavedTime = DateTime.Now;

// Wir können dieses Dokument im Windows Explorer mit der rechten Maustaste anklicken und finden these properties in "Properties" -> "Details" -> "Origin".
doc.Save(ArtifactsDir + "DocumentProperties.Origin.docx");
```

### Siehe auch

* class [BuiltInDocumentProperties](../)
* namensraum [Aspose.Words.Properties](../../builtindocumentproperties/)
* Montage [Aspose.Words](../../../)


