---
title: Font.TintAndShade
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Obtiene o establece un valor doble que aclara u oscurece un color.
type: docs
weight: 520
url: /es/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

Obtiene o establece un valor doble que aclara u oscurece un color.

```csharp
public double TintAndShade { get; set; }
```

### Observaciones

Los valores permitidos están en el rango de -1 (más oscuro) a 1 (más claro) para esta propiedad. Cero (0) es neutral. Intentar establecer esta propiedad en un valor inferior a -1 o superior a 1 da como resultado unArgumentOutOfRangeException.

Establecer esta propiedad para el objeto Fuente con colores no temáticos da como resultado unInvalidOperationException.

### Ejemplos

Muestra cómo crear y utilizar un estilo temático.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Crea un estilo con las propiedades de la fuente del tema.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


