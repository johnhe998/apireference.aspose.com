---
title: BuiltInDocumentProperties.Version
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Stellt die Versionsnummer der Anwendung dar die das Dokument erstellt hat.
type: docs
weight: 320
url: /de/net/aspose.words.properties/builtindocumentproperties/version/
---
## BuiltInDocumentProperties.Version property

Stellt die Versionsnummer der Anwendung dar, die das Dokument erstellt hat.

```csharp
public int Version { get; set; }
```

### Bemerkungen

Wenn ein Dokument von Microsoft Word erstellt wurde, stellen hohe 16-Bit die Hauptversion und niedrige 16-Bit die Build-Nummer dar.

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


