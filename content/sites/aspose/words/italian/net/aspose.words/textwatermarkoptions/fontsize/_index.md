---
title: TextWatermarkOptions.FontSize
second_title: Aspose.Words per .NET API Reference
description: TextWatermarkOptions proprietà. Ottiene o imposta una dimensione del carattere. Il valore predefinito è 0  auto.
type: docs
weight: 40
url: /it/net/aspose.words/textwatermarkoptions/fontsize/
---
## TextWatermarkOptions.FontSize property

Ottiene o imposta una dimensione del carattere. Il valore predefinito è 0 - auto.

```csharp
public float FontSize { get; set; }
```

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentOutOfRangeException | Viene generato quando l'argomento non rientrava nell'intervallo di valori validi. |

### Osservazioni

I valori validi sono compresi tra 0 e 65,5 inclusi.

La dimensione del carattere automatica significa che la filigrana verrà ridimensionata alla sua larghezza massima e altezza massima rispetto a i margini della pagina.

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


