---
title: ImportFormatOptions.ForceCopyStyles
second_title: Aspose.Words per .NET API Reference
description: ImportFormatOptions proprietà. Ottiene o imposta un valore booleano che indica di copiare gli stili in conflitto inKeepSourceFormatting mode. Il valore predefinito èfalso .
type: docs
weight: 20
url: /it/net/aspose.words/importformatoptions/forcecopystyles/
---
## ImportFormatOptions.ForceCopyStyles property

Ottiene o imposta un valore booleano che indica di copiare gli stili in conflitto inKeepSourceFormatting mode. Il valore predefinito è`falso` .

```csharp
public bool ForceCopyStyles { get; set; }
```

### Osservazioni

Per impostazione predefinita, se esiste già uno stile corrispondente in un documento di destinazione, lo stile di origine formatting viene espanso negli attributi del nodo diretto e lo stile di questo nodo viene reimpostato su un valore predefinito.

Quando questa opzione è impostata su`VERO`, lo stile di origine verrà copiato forzatamente nel documento di destinazione con nome univoco e applicato al nodo importato.

Nota, in questo caso non è garantito che la formattazione del nodo importato nella destinazione document venga preservata.

### Esempi

Mostra come copiare forzatamente gli stili di origine con nomi univoci.

```csharp
// Entrambi i documenti contengono MyStyle1 e MyStyle2, MyStyle3 esiste solo in un documento di origine.
Document srcDoc = new Document(MyDir + "Styles source.docx");
Document dstDoc = new Document(MyDir + "Styles destination.docx");

ImportFormatOptions options = new ImportFormatOptions { ForceCopyStyles = true };
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

ParagraphCollection paras = dstDoc.Sections[1].Body.Paragraphs;

Assert.AreEqual(paras[0].ParagraphFormat.Style.Name, "MyStyle1_0");
Assert.AreEqual(paras[1].ParagraphFormat.Style.Name, "MyStyle2_0");
Assert.AreEqual(paras[2].ParagraphFormat.Style.Name, "MyStyle3");
```

### Guarda anche

* class [ImportFormatOptions](../)
* spazio dei nomi [Aspose.Words](../../importformatoptions/)
* assemblea [Aspose.Words](../../../)


