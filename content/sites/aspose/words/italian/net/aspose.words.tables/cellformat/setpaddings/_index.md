---
title: CellFormat.SetPaddings
second_title: Aspose.Words per .NET API Reference
description: CellFormat metodo. Imposta la quantità di spazio in punti da aggiungere a sinistra/in alto/a destra/in basso del contenuto della cella.
type: docs
weight: 160
url: /it/net/aspose.words.tables/cellformat/setpaddings/
---
## CellFormat.SetPaddings method

Imposta la quantità di spazio (in punti) da aggiungere a sinistra/in alto/a destra/in basso del contenuto della cella.

```csharp
public void SetPaddings(double leftPadding, double topPadding, double rightPadding, 
    double bottomPadding)
```

### Esempi

Mostra come riempire il contenuto di una cella con spazi bianchi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Imposta una distanza di riempimento (in punti) tra il bordo e il contenuto del testo
// di ogni cella di tabella che creiamo con il generatore di documenti. 
builder.CellFormat.SetPaddings(5, 10, 40, 50);

// Crea una tabella con una cella il cui contenuto avrà spazi vuoti.
builder.StartTable();
builder.InsertCell();
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

doc.Save(ArtifactsDir + "CellFormat.Padding.docx");
```

### Guarda anche

* class [CellFormat](../)
* spazio dei nomi [Aspose.Words.Tables](../../cellformat/)
* assemblea [Aspose.Words](../../../)


