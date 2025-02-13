---
title: Border.LineStyle
second_title: Aspose.Words per .NET API Reference
description: Border proprietà. Ottiene o imposta lo stile del bordo.
type: docs
weight: 40
url: /it/net/aspose.words/border/linestyle/
---
## Border.LineStyle property

Ottiene o imposta lo stile del bordo.

```csharp
public LineStyle LineStyle { get; set; }
```

### Osservazioni

Se imposti lo stile della linea su nessuno, la larghezza della linea viene automaticamente modificata su zero.

### Esempi

Mostra come inserire una stringa racchiusa da un bordo in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### Guarda anche

* enum [LineStyle](../../linestyle/)
* class [Border](../)
* spazio dei nomi [Aspose.Words](../../border/)
* assemblea [Aspose.Words](../../../)


