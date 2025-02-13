---
title: TextColumnCollection.SetCount
second_title: Aspose.Words per .NET API Reference
description: TextColumnCollection metodo. Dispone il testo nel numero specificato di colonne di testo.
type: docs
weight: 70
url: /it/net/aspose.words/textcolumncollection/setcount/
---
## TextColumnCollection.SetCount method

Dispone il testo nel numero specificato di colonne di testo.

```csharp
public void SetCount(int newCount)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| newCount | Int32 | Il numero di colonne in cui deve essere organizzato il testo. |

### Osservazioni

quando[`EvenlySpaced`](../evenlyspaced/) è **falso** e aumenti il numero di colonne, new[`TextColumn`](../../textcolumn/) gli oggetti vengono creati con larghezza e spaziatura zero. È necessario impostare larghezza e spaziatura per le nuove colonne.

### Esempi

Mostra come creare più colonne equidistanti in una sezione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Guarda anche

* class [TextColumnCollection](../)
* spazio dei nomi [Aspose.Words](../../textcolumncollection/)
* assemblea [Aspose.Words](../../../)


