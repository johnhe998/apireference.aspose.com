---
title: ViewOptions.ZoomType
second_title: Aspose.Words per .NET API Reference
description: ViewOptions proprietà. Ottiene o imposta un valore di zoom in base alle dimensioni della finestra.
type: docs
weight: 60
url: /it/net/aspose.words.settings/viewoptions/zoomtype/
---
## ViewOptions.ZoomType property

Ottiene o imposta un valore di zoom in base alle dimensioni della finestra.

```csharp
public ZoomType ZoomType { get; set; }
```

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

Mostra come impostare un tipo di zoom personalizzato, che le versioni precedenti di Microsoft Word applicheranno a un documento al momento del caricamento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Imposta la proprietà "ZoomType" su "ZoomType.PageWidth" per ottenere Microsoft Word
// per ingrandire automaticamente il documento per adattarlo alla larghezza della pagina.
// Imposta la proprietà "ZoomType" su "ZoomType.FullPage" per ottenere Microsoft Word
// per ingrandire automaticamente il documento per rendere visibile l'intera prima pagina.
// Imposta la proprietà "ZoomType" su "ZoomType.TextFit" per ottenere Microsoft Word
// per ingrandire automaticamente il documento per adattarlo ai margini interni del testo della prima pagina.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Guarda anche

* enum [ZoomType](../../zoomtype/)
* class [ViewOptions](../)
* spazio dei nomi [Aspose.Words.Settings](../../viewoptions/)
* assemblea [Aspose.Words](../../../)


