---
title: SaveOptions.ExportGeneratorName
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Wenn wahr bewirkt dies dass der Name und die Version von Aspose.Words in produzierte Dateien eingebettet werden. Der Standardwert ist Stimmt .
type: docs
weight: 80
url: /de/net/aspose.words.saving/saveoptions/exportgeneratorname/
---
## SaveOptions.ExportGeneratorName property

Wenn wahr, bewirkt dies, dass der Name und die Version von Aspose.Words in produzierte Dateien eingebettet werden. Der Standardwert ist **Stimmt** .

```csharp
public bool ExportGeneratorName { get; set; }
```

### Beispiele

Zeigt, wie das Hinzufügen von Name und Version von Aspose.Words zu produzierten Dateien deaktiviert wird.

```csharp
Document doc = new Document();

// Verwenden Sie https://docs.aspose.com/words/net/generator-or-producer-name-included-in-output-documents/, um zu erfahren, wie Sie das Ergebnis überprüfen können.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { ExportGeneratorName = false };

doc.Save(ArtifactsDir + "OoxmlSaveOptions.ExportGeneratorName.docx", saveOptions);
```

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


