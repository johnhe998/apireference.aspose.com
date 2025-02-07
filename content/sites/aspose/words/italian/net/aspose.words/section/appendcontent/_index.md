---
title: Section.AppendContent
second_title: Aspose.Words per .NET API Reference
description: Section metodo. Inserisce una copia del contenuto della sezione sorgente alla fine di questa sezione.
type: docs
weight: 80
url: /it/net/aspose.words/section/appendcontent/
---
## Section.AppendContent method

Inserisce una copia del contenuto della sezione sorgente alla fine di questa sezione.

```csharp
public void AppendContent(Section sourceSection)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| sourceSection | Section | La sezione da cui copiare il contenuto. |

### Osservazioni

Solo contenuto di[`Body`](../body/) della sezione di origine viene copiato, l'impostazione della pagina, le intestazioni e i piè di pagina di non vengono copiati.

I nodi vengono importati automaticamente se la sezione di origine appartiene a un documento diverso.

Nessuna nuova sezione viene creata nel documento di destinazione.

### Esempi

Mostra come aggiungere il contenuto di una sezione a un'altra sezione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

Section section = doc.Sections[2];

Assert.AreEqual("Section 3" + ControlChar.SectionBreak, section.GetText());

// Inserisce il contenuto della prima sezione all'inizio della terza sezione.
Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

// Inserisce il contenuto della seconda sezione alla fine della terza sezione.
Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);

// I metodi "PrependContent" e "AppendContent" non hanno creato nuove sezioni.
Assert.AreEqual(3, doc.Sections.Count);
Assert.AreEqual("Section 1" + ControlChar.ParagraphBreak +
                "Section 3" + ControlChar.ParagraphBreak +
                "Section 2" + ControlChar.SectionBreak, section.GetText());
```

### Guarda anche

* class [Section](../)
* spazio dei nomi [Aspose.Words](../../section/)
* assemblea [Aspose.Words](../../../)


