---
title: LayoutOptions.TextShaperFactory
second_title: Aspose.Words per .NET API Reference
description: LayoutOptions proprietà. Ottiene o impostaITextShaperFactory implementazione utilizzata per le funzionalità di rendering di tipografia avanzata.
type: docs
weight: 90
url: /it/net/aspose.words.layout/layoutoptions/textshaperfactory/
---
## LayoutOptions.TextShaperFactory property

Ottiene o imposta[`ITextShaperFactory`](../../../aspose.words.shaping/itextshaperfactory/) implementazione utilizzata per le funzionalità di rendering di tipografia avanzata.

```csharp
public ITextShaperFactory TextShaperFactory { get; set; }
```

### Esempi

Mostra come supportare le funzionalità OpenType utilizzando il motore di modellazione del testo HarfBuzz.

```csharp
Document doc = new Document(MyDir + "OpenType text shaping.docx");

// Aspose.Words può utilizzare oggetti di forma del testo forniti esternamente,
// che rappresentano i caratteri e calcolano le informazioni sulla forma del testo.
// Per i documenti che utilizzano più font è necessaria una fabbrica di formattazione del testo.
// Quando lo shaper del testo è impostato in fabbrica, il layout utilizza le funzionalità OpenType.
// Una proprietà Instance restituisce un oggetto statico BasicTextShaperCache che racchiude HarfBuzzTextShaperFactory.
doc.LayoutOptions.TextShaperFactory = HarfBuzzTextShaperFactory.Instance;

// Attualmente, la forma del testo viene eseguita durante l'esportazione nei formati PDF o XPS.
doc.Save(ArtifactsDir + "Document.OpenType.pdf");
```

### Guarda anche

* interface [ITextShaperFactory](../../../aspose.words.shaping/itextshaperfactory/)
* class [LayoutOptions](../)
* spazio dei nomi [Aspose.Words.Layout](../../layoutoptions/)
* assemblea [Aspose.Words](../../../)


