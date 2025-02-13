---
title: MarkdownSaveOptions.ImagesFolder
second_title: Aspose.Words für .NET-API-Referenz
description: MarkdownSaveOptions eigendom. Gibt den physischen Ordner an in dem Bilder gespeichert werden wenn ein Dokument nach exportiert wirdMarkdown Format. Standard ist eine leere Zeichenfolge.
type: docs
weight: 40
url: /de/net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

Gibt den physischen Ordner an, in dem Bilder gespeichert werden, wenn ein Dokument nach exportiert wirdMarkdown Format. Standard ist eine leere Zeichenfolge.

```csharp
public string ImagesFolder { get; set; }
```

### Bemerkungen

Beim Speichern von a[`Document`](../../../aspose.words/document/) inMarkdown format, Aspose.Words muss alle in das Dokument eingebetteten Bilder als eigenständige Dateien speichern. `ImagesFolder` können Sie festlegen, wo die Bilder gespeichert werden.

Wenn Sie ein Dokument in einer Datei speichern und einen Dateinamen angeben, speichert Aspose.Words die Bilder standardmäßig in demselben Ordner, in dem die Dokumentdatei gespeichert ist. Verwenden`ImagesFolder` um dieses Verhalten zu überschreiben.

Wenn Sie ein Dokument in einem Stream speichern, hat Aspose.Words keinen Ordner zum Speichern der Bilder, muss die Bilder aber dennoch irgendwo speichern. In diesem Fall müssen Sie einen zugänglichen Ordner in der angeben`ImagesFolder` Eigentum.

Wenn der angegebene Ordner durch`ImagesFolder` existiert nicht, wird automatisch erstellt.

### Siehe auch

* class [MarkdownSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../markdownsaveoptions/)
* Montage [Aspose.Words](../../../)


