---
title: HtmlFixedSaveOptions.Encoding
second_title: Aspose.Words per .NET API Reference
description: HtmlFixedSaveOptions proprietà. Specifica la codifica da utilizzare durante lesportazione in HTML. Il valore predefinito ènuova codifica UTF8true UTF8 con distinta base.
type: docs
weight: 30
url: /it/net/aspose.words.saving/htmlfixedsaveoptions/encoding/
---
## HtmlFixedSaveOptions.Encoding property

Specifica la codifica da utilizzare durante l'esportazione in HTML. Il valore predefinito è`nuova codifica UTF8(true)` (UTF-8 con distinta base).

```csharp
public Encoding Encoding { get; set; }
```

### Esempi

Mostra come impostare quale codifica utilizzare durante l'esportazione di un documento in HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello World!");

// La codifica predefinita è UTF-8. Se vogliamo rappresentare il nostro documento utilizzando una codifica diversa,
// possiamo usare un oggetto SaveOptions per impostare una codifica specifica.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    Encoding = Encoding.GetEncoding("ASCII")
};

Assert.AreEqual("US-ASCII", htmlFixedSaveOptions.Encoding.EncodingName);

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UseEncoding.html", htmlFixedSaveOptions);
```

### Guarda anche

* class [HtmlFixedSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* assemblea [Aspose.Words](../../../)


