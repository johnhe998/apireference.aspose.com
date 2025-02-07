---
title: Enum TextWrapping
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Tables.TextWrapping enum. Specifica come il testo viene avvolto attorno alla tabella.
type: docs
weight: 6080
url: /it/net/aspose.words.tables/textwrapping/
---
## TextWrapping enumeration

Specifica come il testo viene avvolto attorno alla tabella.

```csharp
public enum TextWrapping
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Il testo e la tabella vengono visualizzati nell'ordine di apparizione nel documento. |
| Around | `1` | Il testo viene avvolto attorno alla tabella occupando lo spazio laterale disponibile. |
| Default | `0` | Valore predefinito. |

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

* spazio dei nomi [Aspose.Words.Tables](../../aspose.words.tables/)
* assemblea [Aspose.Words](../../)


