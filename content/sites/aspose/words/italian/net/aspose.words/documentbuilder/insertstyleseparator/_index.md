---
title: DocumentBuilder.InsertStyleSeparator
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Inserisce il separatore di stile nel documento.
type: docs
weight: 430
url: /it/net/aspose.words/documentbuilder/insertstyleseparator/
---
## DocumentBuilder.InsertStyleSeparator method

Inserisce il separatore di stile nel documento.

```csharp
public void InsertStyleSeparator()
```

### Osservazioni

Questo metodo consente di applicare stili di paragrafo diversi a due parti diverse di una riga di testo.

### Esempi

Mostra come lavorare con i separatori di stile.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ogni paragrafo può avere un solo stile.
// Il metodo InsertStyleSeparator ci consente di aggirare questa limitazione.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("This text is in a Heading style. ");
builder.InsertStyleSeparator();

Style paraStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyParaStyle");
paraStyle.Font.Bold = false;
paraStyle.Font.Size = 8;
paraStyle.Font.Name = "Arial";

builder.ParagraphFormat.StyleName = paraStyle.Name;
builder.Write("This text is in a custom style. ");

// La chiamata al metodo InsertStyleSeparator crea un altro paragrafo,
// che può avere uno stile diverso dal precedente. Non ci saranno interruzioni tra i paragrafi.
// Il testo nel documento di output apparirà come un paragrafo con due stili.
Assert.AreEqual(2, doc.FirstSection.Body.Paragraphs.Count);
Assert.AreEqual("Heading 1", doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.Style.Name);
Assert.AreEqual("MyParaStyle", doc.FirstSection.Body.Paragraphs[1].ParagraphFormat.Style.Name);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertStyleSeparator.docx");
```

### Guarda anche

* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


