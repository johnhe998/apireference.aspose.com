---
title: BuiltInDocumentProperties.Template
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Ruft den informativen Namen der Dokumentvorlage ab oder legt ihn fest.
type: docs
weight: 270
url: /de/net/aspose.words.properties/builtindocumentproperties/template/
---
## BuiltInDocumentProperties.Template property

Ruft den informativen Namen der Dokumentvorlage ab oder legt ihn fest.

```csharp
public string Template { get; set; }
```

### Bemerkungen

In Microsoft Word dient diese Eigenschaft nur zu Informationszwecken und enthält normalerweise nur den Dateinamen der Vorlage ohne den Pfad.

Eine leere Zeichenfolge bedeutet, dass das Dokument an die normale Vorlage angehängt ist.

Verwenden Sie zum Abrufen oder Festlegen des tatsächlichen Namens der angehängten Vorlage the [`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) Eigentum.

### Beispiele

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


