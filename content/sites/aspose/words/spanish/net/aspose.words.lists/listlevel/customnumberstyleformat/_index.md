---
title: ListLevel.CustomNumberStyleFormat
second_title: Referencia de API de Aspose.Words para .NET
description: ListLevel propiedad. Obtiene el formato de estilo de número personalizado para este nivel de lista. Por ejemplo a ç ĝ ....
type: docs
weight: 20
url: /es/net/aspose.words.lists/listlevel/customnumberstyleformat/
---
## ListLevel.CustomNumberStyleFormat property

Obtiene el formato de estilo de número personalizado para este nivel de lista. Por ejemplo: "a, ç, ĝ, ...".

```csharp
public string CustomNumberStyleFormat { get; }
```

### Ejemplos

Muestra cómo obtener el formato de una lista con el estilo de número personalizado.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Podemos obtener valor para el índice especificado del elemento de la lista.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Ver también

* class [ListLevel](../)
* espacio de nombres [Aspose.Words.Lists](../../listlevel/)
* asamblea [Aspose.Words](../../../)


