---
title: DocumentBase.PageColor
second_title: Aspose.Words per .NET API Reference
description: DocumentBase proprietà. Ottiene o imposta il colore della pagina del documento. Questa proprietà è una versione più semplice diBackgroundShape .
type: docs
weight: 60
url: /it/net/aspose.words/documentbase/pagecolor/
---
## DocumentBase.PageColor property

Ottiene o imposta il colore della pagina del documento. Questa proprietà è una versione più semplice di[`BackgroundShape`](../backgroundshape/) .

```csharp
public Color PageColor { get; set; }
```

### Osservazioni

Questa proprietà fornisce un modo semplice per specificare un colore di pagina a tinta unita per il documento. L'impostazione di questa proprietà crea e imposta un[`BackgroundShape`](../backgroundshape/).

Se il colore della pagina non è impostato (es. non c'è una forma di sfondo nel documento) restituisce Empty.

### Esempi

Mostra come impostare il colore di sfondo per tutte le pagine di un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.PageColor = System.Drawing.Color.LightGray;

doc.Save(ArtifactsDir + "DocumentBase.SetPageColor.docx");
```

### Guarda anche

* class [DocumentBase](../)
* spazio dei nomi [Aspose.Words](../../documentbase/)
* assemblea [Aspose.Words](../../../)


