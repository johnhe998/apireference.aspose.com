---
title: HorizontalRuleFormat.Height
second_title: Aspose.Words per .NET API Reference
description: HorizontalRuleFormat proprietà. Ottiene o imposta laltezza della regola orizzontale.
type: docs
weight: 30
url: /it/net/aspose.words.drawing/horizontalruleformat/height/
---
## HorizontalRuleFormat.Height property

Ottiene o imposta l'altezza della regola orizzontale.

```csharp
public double Height { get; set; }
```

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentOutOfRangeException | Viene generato quando l'argomento non rientrava nell'intervallo di valori validi. |

### Osservazioni

Questa è una scorciatoia per il[`Height`](../../shapebase/height/) proprietà.

I valori validi vanno da 0 a 1584 inclusi.

Il valore predefinito è 1,5.

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


