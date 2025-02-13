---
title: BuiltInDocumentProperties.LastPrinted
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Ermittelt oder setzt das Datum an dem das Dokument zuletzt gedruckt wurde in UTC.
type: docs
weight: 150
url: /de/net/aspose.words.properties/builtindocumentproperties/lastprinted/
---
## BuiltInDocumentProperties.LastPrinted property

Ermittelt oder setzt das Datum, an dem das Dokument zuletzt gedruckt wurde, in UTC.

```csharp
public DateTime LastPrinted { get; set; }
```

### Bemerkungen

Für Dokumente, die aus dem RTF-Format stammen, gibt diese Eigenschaft die Ortszeit des letzten Druckvorgangs zurück.

Wenn das Dokument nie gedruckt wurde, gibt diese Eigenschaft DateTime.MinValue zurück.

Aspose.Words aktualisiert diese Eigenschaft nicht.

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


