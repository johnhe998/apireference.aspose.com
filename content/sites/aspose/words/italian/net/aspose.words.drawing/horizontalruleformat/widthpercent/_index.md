---
title: HorizontalRuleFormat.WidthPercent
second_title: Aspose.Words per .NET API Reference
description: HorizontalRuleFormat proprietà. Ottiene o imposta la lunghezza della regola orizzontale specificata espressa come percentuale della larghezza della finestra.
type: docs
weight: 50
url: /it/net/aspose.words.drawing/horizontalruleformat/widthpercent/
---
## HorizontalRuleFormat.WidthPercent property

Ottiene o imposta la lunghezza della regola orizzontale specificata espressa come percentuale della larghezza della finestra.

```csharp
public double WidthPercent { get; set; }
```

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentOutOfRangeException | Viene generato quando l'argomento non rientrava nell'intervallo di valori validi. |

### Osservazioni

I valori validi vanno da 1 a 100 inclusi.

Il valore predefinito è 100.

### Esempi

Mostra come inserire una forma di filetto orizzontale e personalizzarne la formattazione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

Assert.True(shape.IsHorizontalRule);
Assert.True(shape.HorizontalRuleFormat.NoShade);
```

### Guarda anche

* class [HorizontalRuleFormat](../)
* spazio dei nomi [Aspose.Words.Drawing](../../horizontalruleformat/)
* assemblea [Aspose.Words](../../../)


