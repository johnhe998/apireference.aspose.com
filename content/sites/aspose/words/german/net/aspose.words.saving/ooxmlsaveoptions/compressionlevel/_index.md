---
title: OoxmlSaveOptions.CompressionLevel
second_title: Aspose.Words für .NET-API-Referenz
description: OoxmlSaveOptions eigendom. Gibt die zum Speichern des Dokuments verwendete Komprimierungsstufe an. Der Standardwert istNormal .
type: docs
weight: 30
url: /de/net/aspose.words.saving/ooxmlsaveoptions/compressionlevel/
---
## OoxmlSaveOptions.CompressionLevel property

Gibt die zum Speichern des Dokuments verwendete Komprimierungsstufe an. Der Standardwert istNormal .

```csharp
public CompressionLevel CompressionLevel { get; set; }
```

### Beispiele

Zeigt, wie die beim Speichern eines OOXML-Dokuments zu verwendende Komprimierungsstufe angegeben wird.

```csharp
Document doc = new Document(MyDir + "Big document.docx");

// Wenn wir das Dokument in einem OOXML-Format speichern, können wir ein OoxmlSaveOptions-Objekt erstellen
// und dann an die Speichermethode des Dokuments übergeben, um zu ändern, wie wir das Dokument speichern.
// Legen Sie die Eigenschaft "CompressionLevel" auf "CompressionLevel.Maximum" fest, um die stärkste und langsamste Komprimierung anzuwenden.
// Legen Sie die Eigenschaft "CompressionLevel" auf "CompressionLevel.Normal" fest, um sie anzuwenden
// die Standardkomprimierung, die Aspose.Words beim Speichern von OOXML-Dokumenten verwendet.
// Legen Sie die Eigenschaft "CompressionLevel" auf "CompressionLevel.Fast" fest, um eine schnellere und schwächere Komprimierung anzuwenden.
// Setzen Sie die Eigenschaft "CompressionLevel" auf "CompressionLevel.SuperFast", um sie anzuwenden
// die Standardkomprimierung, die Microsoft Word verwendet.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.CompressionLevel = compressionLevel;

Stopwatch st = Stopwatch.StartNew();
doc.Save(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx", saveOptions);
st.Stop();

FileInfo fileInfo = new FileInfo(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx");

Console.WriteLine($"Saving operation done using the \"{compressionLevel}\" compression level:");
Console.WriteLine($"\tDuration:\t{st.ElapsedMilliseconds} ms");
Console.WriteLine($"\tFile Size:\t{fileInfo.Length} bytes");
```

### Siehe auch

* enum [CompressionLevel](../../compressionlevel/)
* class [OoxmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* Montage [Aspose.Words](../../../)


