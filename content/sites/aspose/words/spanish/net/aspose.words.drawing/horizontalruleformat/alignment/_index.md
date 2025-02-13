---
title: HorizontalRuleFormat.Alignment
second_title: Referencia de API de Aspose.Words para .NET
description: HorizontalRuleFormat propiedad. Obtiene o establece la alineación de la regla horizontal.
type: docs
weight: 10
url: /es/net/aspose.words.drawing/horizontalruleformat/alignment/
---
## HorizontalRuleFormat.Alignment property

Obtiene o establece la alineación de la regla horizontal.

```csharp
public HorizontalRuleAlignment Alignment { get; set; }
```

### Observaciones

El valor predeterminado esLeft.

### Ejemplos

Muestra cómo insertar una forma de regla horizontal y personalizar su formato.

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

### Ver también

* enum [HorizontalRuleAlignment](../../horizontalrulealignment/)
* class [HorizontalRuleFormat](../)
* espacio de nombres [Aspose.Words.Drawing](../../horizontalruleformat/)
* asamblea [Aspose.Words](../../../)


