---
title: FixedPageSaveOptions.OptimizeOutput
second_title: Aspose.Words per .NET API Reference
description: FixedPageSaveOptions proprietà. Il flag indica se è necessario ottimizzare loutput. Se questo flag è impostato le tele nidificate ridondanti e le tele vuote vengono rimosse anche i glifi vicini con la stessa formattazione vengono concatenati. Nota la precisione della visualizzazione del contenuto potrebbe essere compromessa se questa proprietà è impostata su true. Limpostazione predefinita è false.
type: docs
weight: 50
url: /it/net/aspose.words.saving/fixedpagesaveoptions/optimizeoutput/
---
## FixedPageSaveOptions.OptimizeOutput property

Il flag indica se è necessario ottimizzare l'output. Se questo flag è impostato, le tele nidificate ridondanti e le tele vuote vengono rimosse, anche i glifi vicini con la stessa formattazione vengono concatenati. Nota: la precisione della visualizzazione del contenuto potrebbe essere compromessa se questa proprietà è impostata su true. L'impostazione predefinita è false.

```csharp
public virtual bool OptimizeOutput { get; set; }
```

### Esempi

Mostra come ottimizzare gli oggetti del documento durante il salvataggio in XP.

```csharp
Document doc = new Document(MyDir + "Unoptimized document.docx");

// Crea un oggetto "XpsSaveOptions" da passare al metodo "Salva" del documento
// per modificare il modo in cui quel metodo converte il documento in .XPS.
XpsSaveOptions saveOptions = new XpsSaveOptions();

// Imposta la proprietà "OptimizeOutput" su "true" per prendere misure come la rimozione di tele nidificate o vuote
// e concatenando esecuzioni adiacenti con formattazione identica per ottimizzare il contenuto del documento di output.
// Ciò potrebbe influire sull'aspetto del documento.
// Imposta la proprietà "OptimizeOutput" su "false" per salvare il documento normalmente.
saveOptions.OptimizeOutput = optimizeOutput;

doc.Save(ArtifactsDir + "XpsSaveOptions.OptimizeOutput.xps", saveOptions);
```

### Guarda anche

* class [FixedPageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* assemblea [Aspose.Words](../../../)


