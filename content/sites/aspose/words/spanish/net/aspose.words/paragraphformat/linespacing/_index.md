---
title: ParagraphFormat.LineSpacing
second_title: Referencia de API de Aspose.Words para .NET
description: ParagraphFormat propiedad. Obtiene o establece el interlineado en puntos del párrafo.
type: docs
weight: 180
url: /es/net/aspose.words/paragraphformat/linespacing/
---
## ParagraphFormat.LineSpacing property

Obtiene o establece el interlineado (en puntos) del párrafo.

```csharp
public double LineSpacing { get; set; }
```

### Observaciones

Cuando la propiedad LineSpacingRule se establece en AtLeast, el espacio entre líneas puede ser mayor o igual que pero nunca menor que el valor de LineSpacing especificado.

Cuando la propiedad LineSpacingRule se establece en Exactamente, el interlineado nunca cambia desde el valor de LineSpacing especificado, incluso si se utiliza una fuente más grande dentro del párrafo.

### Ejemplos

Muestra cómo trabajar con interlineado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// A continuación hay tres reglas de espacio entre líneas que podemos definir usando el
// propiedad "LineSpacingRule" del párrafo para configurar el espaciado entre párrafos.
// 1 - Establecer una cantidad mínima de espacio.
// Esto dará relleno vertical a las líneas de texto de cualquier tamaño
// eso es demasiado pequeño para mantener la altura de línea mínima.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Establecer espaciado exacto.
// El uso de tamaños de fuente demasiado grandes para el espaciado truncará el texto.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Establezca el espaciado como un múltiplo del espaciado de línea predeterminado, que es de 12 puntos de forma predeterminada.
// Este tipo de espaciado se escalará a diferentes tamaños de fuente.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Ver también

* class [ParagraphFormat](../)
* espacio de nombres [Aspose.Words](../../paragraphformat/)
* asamblea [Aspose.Words](../../../)


