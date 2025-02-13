---
title: LayoutOptions.IgnorePrinterMetrics
second_title: Aspose.Words für .NET-API-Referenz
description: LayoutOptions eigendom. Ruft ab oder legt fest ob die Kompatibilitätsoption Druckermaße zum Layout des Dokuments verwenden ignoriert wird. Standard ist True.
type: docs
weight: 50
url: /de/net/aspose.words.layout/layoutoptions/ignoreprintermetrics/
---
## LayoutOptions.IgnorePrinterMetrics property

Ruft ab oder legt fest, ob die Kompatibilitätsoption „Druckermaße zum Layout des Dokuments verwenden“ ignoriert wird. Standard ist True.

```csharp
public bool IgnorePrinterMetrics { get; set; }
```

### Beispiele

Zeigt, wie die Option „Druckermaße zum Layout des Dokuments verwenden“ ignoriert wird.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

doc.LayoutOptions.IgnorePrinterMetrics = false;

doc.Save(ArtifactsDir + "Document.IgnorePrinterMetrics.docx");
```

### Siehe auch

* class [LayoutOptions](../)
* namensraum [Aspose.Words.Layout](../../layoutoptions/)
* Montage [Aspose.Words](../../../)


