---
title: PclSaveOptions.AddPrinterFont
second_title: Aspose.Words für .NET-API-Referenz
description: PclSaveOptions methode. Fügt Informationen über Schriftarten hinzu die vom Hersteller auf den Drucker hochgeladen werden.
type: docs
weight: 50
url: /de/net/aspose.words.saving/pclsaveoptions/addprinterfont/
---
## PclSaveOptions.AddPrinterFont method

Fügt Informationen über Schriftarten hinzu, die vom Hersteller auf den Drucker hochgeladen werden.

```csharp
public void AddPrinterFont(string fontFullName, string fontPclName)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| fontFullName | String | Vollständiger Name der Schriftart (z. B. „Times New Roman Bold Italic“). |
| fontPclName | String | Name der Schriftart, die im Pcl-Dokument verwendet wird. |

### Bemerkungen

Es gibt 52 Schriftarten, die gemäß der Pcl-Spezifikation in jeden Drucker eingebaut werden müssen. Hersteller können jedoch einige andere Schriftarten zu ihren Geräten hinzufügen.

### Beispiele

Zeigt, wie Sie einen Drucker dazu bringen, alle Instanzen einer bestimmten Schriftart durch eine andere Schriftart zu ersetzen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Courier";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.AddPrinterFont("Courier New", "Courier");

// Beim Drucken dieses Dokuments verwendet der Drucker die Schriftart "Courier New".
// um auf Stellen zuzugreifen, an denen unser Dokument die Schriftart "Courier" verwendet hat.
doc.Save(ArtifactsDir + "PclSaveOptions.AddPrinterFont.pcl", saveOptions);
```

### Siehe auch

* class [PclSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pclsaveoptions/)
* Montage [Aspose.Words](../../../)


