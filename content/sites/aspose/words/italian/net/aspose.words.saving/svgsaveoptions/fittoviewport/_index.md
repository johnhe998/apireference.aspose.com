---
title: SvgSaveOptions.FitToViewPort
second_title: Aspose.Words per .NET API Reference
description: SvgSaveOptions proprietà. Specifica se loutput SVG deve riempire larea della finestra disponibile finestra del browser o contenitore. Quando è impostato su true la larghezza e laltezza dellSVG di output sono impostate su 100.
type: docs
weight: 30
url: /it/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

Specifica se l'output SVG deve riempire l'area della finestra disponibile (finestra del browser o contenitore). Quando è impostato su true, la larghezza e l'altezza dell'SVG di output sono impostate su 100%.

Il valore predefinito è falso.

```csharp
public bool FitToViewPort { get; set; }
```

### Esempi

Mostra come imitare le proprietà delle immagini durante la conversione di un documento .docx in .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Configura l'oggetto SvgSaveOptions per il salvataggio senza bordi di pagina o testo selezionabile.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Guarda anche

* class [SvgSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../svgsaveoptions/)
* assemblea [Aspose.Words](../../../)


