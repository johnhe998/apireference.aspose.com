---
title: Font.Spacing
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Devuelve o establece el espaciado en puntos entre caracteres .
type: docs
weight: 380
url: /es/net/aspose.words/font/spacing/
---
## Font.Spacing property

Devuelve o establece el espaciado (en puntos) entre caracteres .

```csharp
public double Spacing { get; set; }
```

### Ejemplos

Muestra cómo configurar la escala horizontal y el espaciado de los caracteres.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Agrega una secuencia de texto y aumenta el ancho de los caracteres al 150%.
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// Agregue tirada de texto y agregue 1 punto de espacio horizontal adicional entre cada carácter.
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// Agrega tirada de texto y acerca los caracteres en 1 punto.
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


