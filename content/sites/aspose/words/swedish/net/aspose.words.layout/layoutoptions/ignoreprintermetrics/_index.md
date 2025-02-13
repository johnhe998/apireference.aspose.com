---
title: LayoutOptions.IgnorePrinterMetrics
second_title: Aspose.Words för .NET API Referens
description: LayoutOptions fast egendom. Hämtar eller ställer in en indikation på om kompatibilitetsalternativet Använd skrivarmått för att lägga ut dokument ignoreras. Standard är True.
type: docs
weight: 50
url: /sv/net/aspose.words.layout/layoutoptions/ignoreprintermetrics/
---
## LayoutOptions.IgnorePrinterMetrics property

Hämtar eller ställer in en indikation på om kompatibilitetsalternativet "Använd skrivarmått för att lägga ut dokument" ignoreras. Standard är True.

```csharp
public bool IgnorePrinterMetrics { get; set; }
```

### Exempel

Visar hur man ignorerar alternativet "Använd skrivarmått för att lägga upp dokument".

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

doc.LayoutOptions.IgnorePrinterMetrics = false;

doc.Save(ArtifactsDir + "Document.IgnorePrinterMetrics.docx");
```

### Se även

* class [LayoutOptions](../)
* namnutrymme [Aspose.Words.Layout](../../layoutoptions/)
* hopsättning [Aspose.Words](../../../)


