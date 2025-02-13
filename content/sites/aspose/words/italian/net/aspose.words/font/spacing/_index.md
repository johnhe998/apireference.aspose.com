---
title: Font.Spacing
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Restituisce o imposta la spaziatura in punti tra i caratteri .
type: docs
weight: 380
url: /it/net/aspose.words/font/spacing/
---
## Font.Spacing property

Restituisce o imposta la spaziatura (in punti) tra i caratteri .

```csharp
public double Spacing { get; set; }
```

### Esempi

Mostra come impostare il ridimensionamento orizzontale e la spaziatura per i caratteri.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aggiungi sequenza di testo e aumenta la larghezza del carattere al 150%.
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// Aggiungi sequenza di testo e aggiungi 1pt di spaziatura orizzontale extra tra ogni carattere.
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// Aggiungi sequenza di testo e avvicina i caratteri di 1pt.
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


