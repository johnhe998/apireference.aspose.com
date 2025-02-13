---
title: Class HorizontalRuleFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.HorizontalRuleFormat clase. Representa formato de regla horizontal.
type: docs
weight: 920
url: /es/net/aspose.words.drawing/horizontalruleformat/
---
## HorizontalRuleFormat class

Representa formato de regla horizontal.

```csharp
public class HorizontalRuleFormat
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Alignment](../../aspose.words.drawing/horizontalruleformat/alignment/) { get; set; } | Obtiene o establece la alineación de la regla horizontal. |
| [Color](../../aspose.words.drawing/horizontalruleformat/color/) { get; set; } | Obtiene o establece el color del pincel que rellena la regla horizontal. |
| [Height](../../aspose.words.drawing/horizontalruleformat/height/) { get; set; } | Obtiene o establece la altura de la regla horizontal. |
| [NoShade](../../aspose.words.drawing/horizontalruleformat/noshade/) { get; set; } | Indica la presencia de sombreado 3D para la regla horizontal. Si es verdadero, entonces la regla horizontal no tiene sombreado 3D y se utiliza un color sólido. |
| [WidthPercent](../../aspose.words.drawing/horizontalruleformat/widthpercent/) { get; set; } | Obtiene o establece la longitud de la regla horizontal especificada expresada como un porcentaje del ancho de la ventana. |

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

* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


