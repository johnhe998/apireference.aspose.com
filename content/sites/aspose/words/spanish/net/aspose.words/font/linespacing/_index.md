---
title: Font.LineSpacing
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Devuelve el interlineado de esta fuente en puntos.
type: docs
weight: 190
url: /es/net/aspose.words/font/linespacing/
---
## Font.LineSpacing property

Devuelve el interlineado de esta fuente (en puntos).

```csharp
public double LineSpacing { get; }
```

### Ejemplos

Muestra cómo obtener el espacio entre líneas de una fuente, en puntos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Configure diferentes fuentes para DocumentBuilder y verifique su interlineado.
builder.Font.Name = "Calibri";
Assert.AreEqual(14.6484375d, builder.Font.LineSpacing);

builder.Font.Name = "Times New Roman";
Assert.AreEqual(13.798828125d, builder.Font.LineSpacing);
```

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


