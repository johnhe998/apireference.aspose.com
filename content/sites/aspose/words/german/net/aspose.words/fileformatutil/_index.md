---
title: Class FileFormatUtil
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.FileFormatUtil klas. Stellt Dienstprogrammmethoden für die Arbeit mit Dateiformaten bereit z. B. das Erkennen des Dateiformats oder das Konvertieren von Dateierweiterungen in/aus Dateiformataufzählungen.
type: docs
weight: 2640
url: /de/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

Stellt Dienstprogrammmethoden für die Arbeit mit Dateiformaten bereit, z. B. das Erkennen des Dateiformats oder das Konvertieren von Dateierweiterungen in/aus Dateiformataufzählungen.

```csharp
public static class FileFormatUtil
```

## Methoden

| Name | Beschreibung |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | Konvertiert den IANA-Inhaltstyp in einen Aufzählungswert im Ladeformat. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | Konvertiert den IANA-Inhaltstyp in einen Aufzählungswert im Speicherformat. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | Erkennt und gibt die Informationen über ein Format eines in einem Stream gespeicherten Dokuments zurück. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | Erkennt Informationen über ein Format eines Dokuments, das in einer Festplattendatei gespeichert ist, und gibt sie zurück. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | Konvertiert eine Dateinamenerweiterung in a[`SaveFormat`](../saveformat/) wert. |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | Konvertiert einen Aufzählungswert des Bildtyps Aspose.Words in eine Dateierweiterung. Die zurückgegebene Erweiterung ist eine Zeichenfolge in Kleinbuchstaben mit einem führenden Punkt. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | Wandelt einen Aufzählungswert im Ladeformat in eine Dateierweiterung um. Die zurückgegebene Erweiterung ist eine Zeichenfolge in Kleinbuchstaben mit einem führenden Punkt. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | Konvertiert a[`LoadFormat`](../loadformat/) Wert zu a[`SaveFormat`](../saveformat/) Wert wenn möglich. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | Konvertiert einen Aufzählungswert im Speicherformat in eine Dateierweiterung. Die zurückgegebene Erweiterung ist eine Zeichenfolge in Kleinbuchstaben mit einem führenden Punkt. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | Konvertiert a[`SaveFormat`](../saveformat/) Wert zu a[`LoadFormat`](../loadformat/) Wert wenn möglich. |

### Beispiele

Zeigt, wie die Kodierung in einer HTML-Datei erkannt wird.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// Die Encoding-Eigenschaft wird nur verwendet, wenn wir ein FileFormatInfo-Objekt für ein HTML-Dokument erstellen.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


