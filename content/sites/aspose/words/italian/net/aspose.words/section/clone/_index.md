---
title: Section.Clone
second_title: Aspose.Words per .NET API Reference
description: Section metodo. Crea un duplicato di questa sezione.
type: docs
weight: 110
url: /it/net/aspose.words/section/clone/
---
## Section.Clone method

Crea un duplicato di questa sezione.

```csharp
public Section Clone()
```

### Esempi

Mostra come aggiungere e rimuovere sezioni in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// Elimina la prima sezione dal documento.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// Aggiungi una copia di quella che ora è la prima sezione alla fine del documento.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### Guarda anche

* class [Section](../)
* spazio dei nomi [Aspose.Words](../../section/)
* assemblea [Aspose.Words](../../../)


