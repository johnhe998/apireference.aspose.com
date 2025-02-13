---
title: ParagraphFormat.LineSpacingRule
second_title: Aspose.Words per .NET API Reference
description: ParagraphFormat proprietà. Ottiene o imposta linterlinea per il paragrafo.
type: docs
weight: 190
url: /it/net/aspose.words/paragraphformat/linespacingrule/
---
## ParagraphFormat.LineSpacingRule property

Ottiene o imposta l'interlinea per il paragrafo.

```csharp
public LineSpacingRule LineSpacingRule { get; set; }
```

### Esempi

Mostra come lavorare con l'interlinea.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Di seguito sono riportate tre regole di interlinea che possiamo definire utilizzando il
// Proprietà "LineSpacingRule" del paragrafo per configurare la spaziatura tra i paragrafi.
// 1 - Imposta una quantità minima di spaziatura.
// Questo darà il riempimento verticale alle righe di testo di qualsiasi dimensione
// che è troppo piccolo per mantenere l'altezza di riga minima.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Imposta la spaziatura esatta.
// L'uso di caratteri di dimensioni troppo grandi per la spaziatura troncherà il testo.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Imposta l'interlinea come multiplo dell'interlinea predefinita, che è di 12 punti per impostazione predefinita.
// Questo tipo di spaziatura verrà ridimensionata in base a diverse dimensioni dei caratteri.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Guarda anche

* enum [LineSpacingRule](../../linespacingrule/)
* class [ParagraphFormat](../)
* spazio dei nomi [Aspose.Words](../../paragraphformat/)
* assemblea [Aspose.Words](../../../)


