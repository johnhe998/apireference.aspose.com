---
title: ParagraphFormat.SnapToGrid
second_title: Aspose.Words per .NET API Reference
description: ParagraphFormat proprietà. Specifica se il paragrafo corrente deve utilizzare le linee della griglia del documento per le impostazioni di pagina durante la disposizione dei contenuti nel paragrafo.
type: docs
weight: 280
url: /it/net/aspose.words/paragraphformat/snaptogrid/
---
## ParagraphFormat.SnapToGrid property

Specifica se il paragrafo corrente deve utilizzare le linee della griglia del documento per le impostazioni di pagina durante la disposizione dei contenuti nel paragrafo.

```csharp
public bool SnapToGrid { get; set; }
```

### Esempi

Mostra come specificare un limite per il numero di righe che ciascuna pagina può avere.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Abilita il pitching, quindi utilizzalo per impostare il numero di righe per pagina in questa sezione.
// Una dimensione del carattere sufficientemente grande spingerà alcune righe nella pagina successiva per evitare la sovrapposizione dei caratteri.
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### Guarda anche

* class [ParagraphFormat](../)
* spazio dei nomi [Aspose.Words](../../paragraphformat/)
* assemblea [Aspose.Words](../../../)


