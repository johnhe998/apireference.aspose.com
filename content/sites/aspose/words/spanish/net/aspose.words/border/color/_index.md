---
title: Border.Color
second_title: Referencia de API de Aspose.Words para .NET
description: Border propiedad. Obtiene o establece el color del borde.
type: docs
weight: 10
url: /es/net/aspose.words/border/color/
---
## Border.Color property

Obtiene o establece el color del borde.

```csharp
public Color Color { get; set; }
```

### Ejemplos

Muestra cómo insertar una cadena rodeada por un borde en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### Ver también

* class [Border](../)
* espacio de nombres [Aspose.Words](../../border/)
* asamblea [Aspose.Words](../../../)


