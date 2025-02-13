---
title: Enum DmlEffectsRenderingMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.DmlEffectsRenderingMode enum. Specifica la modalità di rendering degli effetti DrawingML in formati di pagina fissi.
type: docs
weight: 4650
url: /it/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

Specifica la modalità di rendering degli effetti DrawingML in formati di pagina fissi.

```csharp
public enum DmlEffectsRenderingMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Simplified | `0` | Il rendering degli effetti DrawingML è semplificato. |
| None | `1` | Nessun effetto DrawingML viene renderizzato. |
| Fine | `2` | Gli effetti DrawingML sono renderizzati in modalità fine che implica un'elaborazione avanzata. In questa modalità il rendering degli effetti fornisce risultati migliori ma a un costo di prestazioni maggiore rispetto aSimplified modalità. |

### Esempi

Mostra come configurare la qualità di rendering degli effetti DrawingML in un documento mentre lo salviamo in PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "DmlEffectsRenderingMode" su "DmlEffectsRenderingMode.None" per eliminare tutti gli effetti DrawingML.
// Imposta la proprietà "DmlEffectsRenderingMode" su "DmlEffectsRenderingMode.Simplified"
// per eseguire il rendering di una versione semplificata degli effetti DrawingML.
// Imposta la proprietà "DmlEffectsRenderingMode" su "DmlEffectsRenderingMode.Fine" su
// renderizza gli effetti di DrawingML con maggiore precisione e anche con maggiori costi di elaborazione.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


