---
title: PclSaveOptions.FallbackFontName
second_title: Aspose.Words für .NET-API-Referenz
description: PclSaveOptions eigendom. Name der Schriftart die verwendet wird wenn keine erwartete Schriftart in den Drucker und integrierten Schriftartensammlungen gefunden wird.
type: docs
weight: 20
url: /de/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

Name der Schriftart, die verwendet wird, wenn keine erwartete Schriftart in den Drucker- und integrierten Schriftartensammlungen gefunden wird.

```csharp
public string FallbackFontName { get; set; }
```

### Bemerkungen

Wenn kein Fallback gefunden wird, wird eine Warnung generiert und die Schriftart „Arial“ verwendet.

### Beispiele

Zeigt, wie eine Schriftart deklariert wird, die ein Drucker als Ersatz auf gedruckten Text anwendet, falls die ursprüngliche Schriftart nicht verfügbar ist.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// Dieses Dokument weist den Drucker an, "Times New Roman" auf den Text mit der fehlenden Schriftart anzuwenden.
// Sollte "Times New Roman" ebenfalls nicht verfügbar sein, verwendet der Drucker standardmäßig die Schriftart "Arial".
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### Siehe auch

* class [PclSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pclsaveoptions/)
* Montage [Aspose.Words](../../../)


