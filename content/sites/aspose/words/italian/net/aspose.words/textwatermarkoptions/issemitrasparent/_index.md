---
title: TextWatermarkOptions.IsSemitrasparent
second_title: Aspose.Words per .NET API Reference
description: TextWatermarkOptions proprietà. Ottiene o imposta un valore booleano responsabile dellopacità della filigrana. Il valore predefinito è True.
type: docs
weight: 50
url: /it/net/aspose.words/textwatermarkoptions/issemitrasparent/
---
## TextWatermarkOptions.IsSemitrasparent property

Ottiene o imposta un valore booleano responsabile dell'opacità della filigrana. Il valore predefinito è True.

```csharp
public bool IsSemitrasparent { get; set; }
```

### Esempi

Mostra come creare una filigrana di testo.

```csharp
Document doc = new Document();

// Aggiungi una filigrana di testo normale.
doc.Watermark.SetText("Aspose Watermark");

// Se desideriamo modificare la formattazione del testo usandola come filigrana,
// possiamo farlo passando un oggetto TextWatermarkOptions durante la creazione della filigrana.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Possiamo rimuovere una filigrana da un documento come questo.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Guarda anche

* class [TextWatermarkOptions](../)
* spazio dei nomi [Aspose.Words](../../textwatermarkoptions/)
* assemblea [Aspose.Words](../../../)


