---
title: HtmlLoadOptions.SupportVml
second_title: Aspose.Words per .NET API Reference
description: HtmlLoadOptions proprietà. Ottiene o imposta un valore che indica se supportare le immagini VML.
type: docs
weight: 60
url: /it/net/aspose.words.loading/htmlloadoptions/supportvml/
---
## HtmlLoadOptions.SupportVml property

Ottiene o imposta un valore che indica se supportare le immagini VML.

```csharp
public bool SupportVml { get; set; }
```

### Esempi

Mostra come supportare i commenti condizionali durante il caricamento di un documento HTML.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// Se il valore è true, prendiamo in considerazione il codice VML durante l'analisi del documento caricato.
loadOptions.SupportVml = supportVml;

// Questo documento contiene un'immagine JPEG all'interno di "<!--[if gte vml 1]>" tag,
// e un'immagine PNG diversa all'interno di "<![if !vml]>" tag.
// Se impostiamo il flag "SupportVml" su "true", Aspose.Words caricherà il JPEG.
// Se impostiamo questo flag su "false", Aspose.Words caricherà solo il PNG.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### Guarda anche

* class [HtmlLoadOptions](../)
* spazio dei nomi [Aspose.Words.Loading](../../htmlloadoptions/)
* assemblea [Aspose.Words](../../../)


