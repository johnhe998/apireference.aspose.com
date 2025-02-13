---
title: HtmlFixedSaveOptions.OptimizeOutput
second_title: Aspose.Words per .NET API Reference
description: HtmlFixedSaveOptions proprietà. Il flag indica se è necessario ottimizzare loutput. Se questo flag è impostato le tele nidificate ridondanti e le tele vuote vengono rimosse anche i glifi vicini con la stessa formattazione vengono concatenati. Nota la precisione della visualizzazione del contenuto potrebbe essere compromessa se questa proprietà è impostata su true. Limpostazione predefinita è true.
type: docs
weight: 100
url: /it/net/aspose.words.saving/htmlfixedsaveoptions/optimizeoutput/
---
## HtmlFixedSaveOptions.OptimizeOutput property

Il flag indica se è necessario ottimizzare l'output. Se questo flag è impostato, le tele nidificate ridondanti e le tele vuote vengono rimosse, anche i glifi vicini con la stessa formattazione vengono concatenati. Nota: la precisione della visualizzazione del contenuto potrebbe essere compromessa se questa proprietà è impostata su true. L'impostazione predefinita è true.

```csharp
public override bool OptimizeOutput { get; set; }
```

### Esempi

Mostra come semplificare un documento durante il salvataggio in HTML rimuovendo vari oggetti ridondanti.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { OptimizeOutput = optimizeOutput };

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html", saveOptions);

// La dimensione della versione ottimizzata del documento è quasi un terzo della dimensione del documento non ottimizzato.
Assert.AreEqual(optimizeOutput ? 62521 : 191770,
    new FileInfo(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html").Length, 200);
```

### Guarda anche

* class [HtmlFixedSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* assemblea [Aspose.Words](../../../)


