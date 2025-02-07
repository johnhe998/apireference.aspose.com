---
title: FindReplaceOptions.ApplyParagraphFormat
second_title: Aspose.Words per .NET API Reference
description: FindReplaceOptions proprietà. Formattazione del paragrafo applicata al nuovo contenuto.
type: docs
weight: 30
url: /it/net/aspose.words.replacing/findreplaceoptions/applyparagraphformat/
---
## FindReplaceOptions.ApplyParagraphFormat property

Formattazione del paragrafo applicata al nuovo contenuto.

```csharp
public ParagraphFormat ApplyParagraphFormat { get; }
```

### Esempi

Mostra come aggiungere la formattazione ai paragrafi in cui un'operazione trova e sostituisci ha trovato corrispondenze.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Every paragraph that ends with a full stop like this one will be right aligned.");
builder.Writeln("This one will not!");
builder.Write("This one also will.");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(ParagraphAlignment.Left, paragraphs[0].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[1].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[2].ParagraphFormat.Alignment);

// Possiamo usare un oggetto "FindReplaceOptions" per modificare il processo di ricerca e sostituzione.
FindReplaceOptions options = new FindReplaceOptions();

// Imposta la proprietà "Alignment" su "ParagraphAlignment.Right" per allineare a destra ogni paragrafo
// che contiene una corrispondenza trovata dall'operazione trova e sostituisci.
options.ApplyParagraphFormat.Alignment = ParagraphAlignment.Right;

// Sostituisci ogni punto fermo prima di un'interruzione di paragrafo con un punto esclamativo.
int count = doc.Range.Replace(".&p", "!&p", options);

Assert.AreEqual(2, count);
Assert.AreEqual(ParagraphAlignment.Right, paragraphs[0].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[1].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Right, paragraphs[2].ParagraphFormat.Alignment);
Assert.AreEqual("Every paragraph that ends with a full stop like this one will be right aligned!\r" +
                "This one will not!\r" +
                "This one also will!", doc.GetText().Trim());
```

### Guarda anche

* class [ParagraphFormat](../../../aspose.words/paragraphformat/)
* class [FindReplaceOptions](../)
* spazio dei nomi [Aspose.Words.Replacing](../../findreplaceoptions/)
* assemblea [Aspose.Words](../../../)


