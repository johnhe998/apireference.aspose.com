---
title: Enum ViewType
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Settings.ViewType enum. Possibili valori per la modalità di visualizzazione in Microsoft Word.
type: docs
weight: 5660
url: /it/net/aspose.words.settings/viewtype/
---
## ViewType enumeration

Possibili valori per la modalità di visualizzazione in Microsoft Word.

```csharp
public enum ViewType
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Il documento deve essere visualizzato nella visualizzazione predefinita dell'applicazione. |
| Reading | `0` | Il documento deve essere visualizzato nella visualizzazione predefinita dell'applicazione. |
| PageLayout | `1` | Il documento verrà aperto in una vista che visualizzi il documento mentre verrà stampato. |
| Outline | `3` | Il documento deve essere reso in una vista ottimizzata per delineare o creare documenti lunghi. |
| Normal | `4` | Il documento deve essere reso in una vista ottimizzata per delineare o creare documenti lunghi. |
| Web | `5` | Il documento deve essere reso in una vista che imita il modo in cui questo documento verrebbe visualizzato in una pagina web. |

### Esempi

Mostra come impostare un fattore di zoom personalizzato, che le versioni precedenti di Microsoft Word applicheranno a un documento al momento del caricamento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

### Guarda anche

* class [ViewOptions](../viewoptions/)
* property [ViewType](../viewoptions/viewtype/)
* spazio dei nomi [Aspose.Words.Settings](../../aspose.words.settings/)
* assemblea [Aspose.Words](../../)


