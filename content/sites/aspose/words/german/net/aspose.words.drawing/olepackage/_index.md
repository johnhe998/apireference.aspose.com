---
title: Class OlePackage
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.OlePackage klas. Ermöglicht den Zugriff auf OLEPaketeigenschaften.
type: docs
weight: 1030
url: /de/net/aspose.words.drawing/olepackage/
---
## OlePackage class

Ermöglicht den Zugriff auf OLE-Paketeigenschaften.

```csharp
public class OlePackage
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DisplayName](../../aspose.words.drawing/olepackage/displayname/) { get; set; } | Ruft den Anzeigenamen des OLE-Pakets ab oder legt ihn fest. |
| [FileName](../../aspose.words.drawing/olepackage/filename/) { get; set; } | Ruft den Dateinamen des OLE-Pakets ab oder legt ihn fest. |

### Bemerkungen

Das OLE-Paket ist eine veraltete und "undokumentierte" Möglichkeit, eingebettete Objekte zu speichern, wenn der OLE-Handler unbekannt ist. Frühe Windows-Versionen wie Windows 3.1, 95 und 98 hatten die Anwendung "Packager.exe", mit der alle Arten von Daten in ein Dokument eingebettet werden konnten . Jetzt ist diese Anwendung von Windows ausgeschlossen, aber MS Word und andere Anwendungen verwenden sie weiterhin zum Einbetten von Daten, wenn der OLE-Handler fehlt oder unbekannt ist.

### Beispiele

Zeigt, wie ein OLE-Objekt in ein Dokument eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// OLE-Objekte ermöglichen es uns, andere Dateien im lokalen Dateisystem mit einer anderen installierten Anwendung zu öffnen
// in unserem Betriebssystem durch Doppelklicken auf die Form, die das OLE-Objekt im Dokumentkörper enthält.
// In diesem Fall ist unsere externe Datei ein ZIP-Archiv.
byte[] zipFileBytes = File.ReadAllBytes(DatabaseDir + "cat001.zip");

using (MemoryStream stream = new MemoryStream(zipFileBytes))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);

    shape.OleFormat.OlePackage.FileName = "Package file name.zip";
    shape.OleFormat.OlePackage.DisplayName = "Package display name.zip";
}

doc.Save(ArtifactsDir + "Shape.InsertOlePackage.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


