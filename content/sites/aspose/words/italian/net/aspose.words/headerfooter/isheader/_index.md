---
title: HeaderFooter.IsHeader
second_title: Aspose.Words per .NET API Reference
description: HeaderFooter proprietà. Vero se questo HeaderFooter loggetto è unintestazione.
type: docs
weight: 30
url: /it/net/aspose.words/headerfooter/isheader/
---
## HeaderFooter.IsHeader property

Vero se questo **HeaderFooter** l'oggetto è un'intestazione.

```csharp
public bool IsHeader { get; }
```

### Esempi

Mostra come creare un'intestazione e un piè di pagina.

```csharp
Document doc = new Document();

// Crea un'intestazione e aggiungi un paragrafo ad essa. Il testo in quel paragrafo
// apparirà nella parte superiore di ogni pagina di questa sezione, sopra il corpo del testo principale.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// Crea un piè di pagina e aggiungi un paragrafo. Il testo in quel paragrafo
// apparirà in fondo a ogni pagina di questa sezione, sotto il corpo del testo principale.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### Guarda anche

* class [HeaderFooter](../)
* spazio dei nomi [Aspose.Words](../../headerfooter/)
* assemblea [Aspose.Words](../../../)


