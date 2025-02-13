---
title: Enum SvgTextOutputMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.SvgTextOutputMode enum. 
type: docs
weight: 5330
url: /it/net/aspose.words.saving/svgtextoutputmode/
---
## SvgTextOutputMode enumeration

```csharp
public enum SvgTextOutputMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| UseSvgFonts | `0` | I caratteri SVG vengono utilizzati per il rendering del testo. Nota, non tutti i browser supportano i caratteri SVG. |
| UseTargetMachineFonts | `1` | I caratteri installati sulla macchina di destinazione vengono utilizzati per il rendering del testo. Nota, se alcuni dei font utilizzati nel documento non sono disponibili sulla macchina di destinazione, il documento potrebbe avere un aspetto diverso. |
| UsePlacedGlyphs | `2` | Il testo viene visualizzato utilizzando le curve. Nota, la selezione del testo non funzionerà se utilizzi questa opzione. |

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

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


