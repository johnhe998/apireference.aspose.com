---
title: Chart.SourceFullName
second_title: Aspose.Words per .NET API Reference
description: Chart proprietà. Ottiene il percorso e il nome di un file xls/xlsx a cui questo grafico è collegato.
type: docs
weight: 60
url: /it/net/aspose.words.drawing.charts/chart/sourcefullname/
---
## Chart.SourceFullName property

Ottiene il percorso e il nome di un file xls/xlsx a cui questo grafico è collegato.

```csharp
public string SourceFullName { get; set; }
```

### Esempi

Mostra come ottenere il nome completo del documento xls/xlsx esterno se il grafico è collegato.

```csharp
Document doc = new Document(MyDir + "Shape with linked chart.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.True(shape.Chart.SourceFullName.Contains("Examples\\Data\\Spreadsheet.xlsx"));
```

### Guarda anche

* class [Chart](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chart/)
* assemblea [Aspose.Words](../../../)


