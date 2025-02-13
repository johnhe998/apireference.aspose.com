---
title: TextColumn.Width
second_title: Aspose.Words per .NET API Reference
description: TextColumn proprietà. Ottiene o imposta la larghezza della colonna di testo in punti.
type: docs
weight: 20
url: /it/net/aspose.words/textcolumn/width/
---
## TextColumn.Width property

Ottiene o imposta la larghezza della colonna di testo in punti.

```csharp
public double Width { get; set; }
```

### Esempi

Mostra come creare colonne con spaziatura non uniforme.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Determina la quantità di spazio disponibile per la disposizione delle colonne.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Imposta la prima colonna in modo che sia stretta.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Imposta la seconda colonna per occupare il resto dello spazio disponibile all'interno dei margini della pagina.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Guarda anche

* class [TextColumn](../)
* spazio dei nomi [Aspose.Words](../../textcolumn/)
* assemblea [Aspose.Words](../../../)


