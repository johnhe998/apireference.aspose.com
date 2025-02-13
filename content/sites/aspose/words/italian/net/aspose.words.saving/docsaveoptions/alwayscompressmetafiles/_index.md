---
title: DocSaveOptions.AlwaysCompressMetafiles
second_title: Aspose.Words per .NET API Reference
description: DocSaveOptions proprietà. Quandofalso  i metafile di piccole dimensioni non vengono compressi per motivi di prestazioni. Il valore predefinito è VERO  tutti i metafile vengono compressi indipendentemente dalle dimensioni.
type: docs
weight: 20
url: /it/net/aspose.words.saving/docsaveoptions/alwayscompressmetafiles/
---
## DocSaveOptions.AlwaysCompressMetafiles property

Quando`falso` , i metafile di piccole dimensioni non vengono compressi per motivi di prestazioni. Il valore predefinito è **VERO** , tutti i metafile vengono compressi indipendentemente dalle dimensioni.

```csharp
public bool AlwaysCompressMetafiles { get; set; }
```

### Esempi

Mostra come modificare la compressione dei metafile in un documento durante il salvataggio.

```csharp
// Apre un documento che contiene una formula di Microsoft Equation 3.0.
Document doc = new Document(MyDir + "Microsoft equation object.docx");

// Quando salviamo un documento, i metafile più piccoli non vengono compressi per motivi di prestazioni.
// Possiamo impostare un flag in un oggetto SaveOptions per comprimere ogni metafile durante il salvataggio.
// Alcuni editor come LibreOffice non possono leggere metafile non compressi.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.AlwaysCompressMetafiles = compressAllMetafiles;

doc.Save(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx", saveOptions);

if (compressAllMetafiles)
    Assert.That(10000, Is.LessThan(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
else
    Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
```

### Guarda anche

* class [DocSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../docsaveoptions/)
* assemblea [Aspose.Words](../../../)


