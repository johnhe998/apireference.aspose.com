---
title: Table.TextWrapping
second_title: Aspose.Words per .NET API Reference
description: Table proprietà. Ottiene o impostaTextWrapping per la tavola.
type: docs
weight: 310
url: /it/net/aspose.words.tables/table/textwrapping/
---
## Table.TextWrapping property

Ottiene o imposta`TextWrapping` per la tavola.

```csharp
public TextWrapping TextWrapping { get; set; }
```

### Esempi

Mostra come lavorare con il ritorno a capo del testo della tabella.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

builder.Font.Size = 16;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Imposta la proprietà "TextWrapping" su "TextWrapping.Around" per fare in modo che la tabella disponga del testo attorno ad essa,
// e spingilo verso il basso nel paragrafo sottostante impostando la posizione.
table.TextWrapping = TextWrapping.Around;
table.AbsoluteHorizontalDistance = 100;
table.AbsoluteVerticalDistance = 20;

doc.Save(ArtifactsDir + "Table.WrapText.docx");
```

### Guarda anche

* enum [TextWrapping](../../textwrapping/)
* class [Table](../)
* spazio dei nomi [Aspose.Words.Tables](../../table/)
* assemblea [Aspose.Words](../../../)


