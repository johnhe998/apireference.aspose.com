---
title: ControlChar.Tab
second_title: Referencia de API de Aspose.Words para .NET
description: ControlChar campo. Carácter de tabulación x0009 o t.
type: docs
weight: 270
url: /es/net/aspose.words/controlchar/tab/
---
## ControlChar.Tab field

Carácter de tabulación: "\x0009" o "\t".

```csharp
public static readonly string Tab;
```

### Ejemplos

Muestra cómo establecer un intervalo personalizado para las posiciones de tabulación.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Establecer tabulaciones para que aparezcan cada 72 puntos (1 pulgada).
builder.Document.DefaultTabStop = 72;

// Cada carácter de tabulación ajusta el texto que le sigue a la siguiente posición de tabulación más cercana.
builder.Writeln("Hello" + ControlChar.Tab + "World!");
builder.Writeln("Hello" + ControlChar.TabChar + "World!");
```

### Ver también

* class [ControlChar](../)
* espacio de nombres [Aspose.Words](../../controlchar/)
* asamblea [Aspose.Words](../../../)


