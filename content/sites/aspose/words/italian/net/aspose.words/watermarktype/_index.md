---
title: Enum WatermarkType
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.WatermarkType enum. Specifica il tipo di filigrana.
type: docs
weight: 6380
url: /it/net/aspose.words/watermarktype/
---
## WatermarkType enumeration

Specifica il tipo di filigrana.

```csharp
public enum WatermarkType
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Text | `0` | Indica che il testo verrà utilizzato come filigrana. |
| Image | `1` | Indica che l'immagine verrà utilizzata come filigrana. |
| None | `2` | Indica che la filigrana non è impostata. |

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

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


