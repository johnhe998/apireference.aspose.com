---
title: TextColumnCollection.EvenlySpaced
second_title: Aspose.Words per .NET API Reference
description: TextColumnCollection proprietà. Vero se le colonne di testo sono di uguale larghezza e spaziate uniformemente.
type: docs
weight: 20
url: /it/net/aspose.words/textcolumncollection/evenlyspaced/
---
## TextColumnCollection.EvenlySpaced property

**Vero** se le colonne di testo sono di uguale larghezza e spaziate uniformemente.

```csharp
public bool EvenlySpaced { get; set; }
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

* class [TextColumnCollection](../)
* spazio dei nomi [Aspose.Words](../../textcolumncollection/)
* assemblea [Aspose.Words](../../../)


