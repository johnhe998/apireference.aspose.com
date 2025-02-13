---
title: Shape.HorizontalRuleFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Shape propiedad. Proporciona acceso a las propiedades de la forma de regla horizontal. Para una forma que no es una regla horizontal devuelve nulo.
type: docs
weight: 100
url: /es/net/aspose.words.drawing/shape/horizontalruleformat/
---
## Shape.HorizontalRuleFormat property

Proporciona acceso a las propiedades de la forma de regla horizontal. Para una forma que no es una regla horizontal, devuelve nulo.

```csharp
public HorizontalRuleFormat HorizontalRuleFormat { get; }
```

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

* class [HorizontalRuleFormat](../../horizontalruleformat/)
* class [Shape](../)
* espacio de nombres [Aspose.Words.Drawing](../../shape/)
* asamblea [Aspose.Words](../../../)


