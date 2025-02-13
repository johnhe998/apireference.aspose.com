---
title: Enum DmlRenderingMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.DmlRenderingMode enum. Specifica come vengono renderizzate le forme DrawingML in formati di pagina fissi.
type: docs
weight: 4660
url: /it/net/aspose.words.saving/dmlrenderingmode/
---
## DmlRenderingMode enumeration

Specifica come vengono renderizzate le forme DrawingML in formati di pagina fissi.

```csharp
public enum DmlRenderingMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Fallback | `0` | Se la forma di riserva è disponibile per DrawingML, Aspose.Words esegue il rendering della forma di riserva invece di DrawingML. |
| DrawingML | `1` | Aspose.Words ignora la forma di fallback di DrawingML e esegue il rendering di DrawingML stesso. Questa è la modalità predefinita. |

### Esempi

Mostra come eseguire il rendering di forme di riserva durante il salvataggio in PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "DmlRenderingMode" su "DmlRenderingMode.Fallback"
// per sostituire le forme DML con le loro forme di riserva.
// Imposta la proprietà "DmlRenderingMode" su "DmlRenderingMode.DrawingML"
// per renderizzare le forme DML stesse.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

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


