---
title: StyleCollection.ClearQuickStyleGallery
second_title: Aspose.Words per .NET API Reference
description: StyleCollection metodo. Rimuove tutti gli stili dal pannello Galleria di stili rapidi.
type: docs
weight: 80
url: /it/net/aspose.words/stylecollection/clearquickstylegallery/
---
## StyleCollection.ClearQuickStyleGallery method

Rimuove tutti gli stili dal pannello Galleria di stili rapidi.

```csharp
public void ClearQuickStyleGallery()
```

### Esempi

Mostra come rimuovere gli stili dal pannello Galleria di stili.

```csharp
Document doc = new Document();

// Nota che per ora gli stili di rimozione funzionano solo con il formato DOCX.
doc.Styles.ClearQuickStyleGallery();

doc.Save(ArtifactsDir + "Styles.RemoveStylesFromStyleGallery.docx");
```

### Guarda anche

* class [StyleCollection](../)
* spazio dei nomi [Aspose.Words](../../stylecollection/)
* assemblea [Aspose.Words](../../../)


