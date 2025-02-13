---
title: ListFormat.ListIndent
second_title: Referencia de API de Aspose.Words para .NET
description: ListFormat método. Aumenta el nivel de lista del párrafo actual en un nivel.
type: docs
weight: 70
url: /es/net/aspose.words.lists/listformat/listindent/
---
## ListFormat.ListIndent method

Aumenta el nivel de lista del párrafo actual en un nivel.

```csharp
public void ListIndent()
```

### Observaciones

Este método cambia el nivel de la lista y aplica las propiedades de formato del nuevo nivel.

En los documentos de Word, las listas pueden constar de hasta nueve niveles. El formato de lista para cada nivel especifica qué viñeta o número se usa, sangría izquierda, espacio entre la viñeta y el texto, etc.

### Ejemplos

Muestra cómo crear listas numeradas y con viñetas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Aspose.Words main advantages are:");

// Una lista nos permite organizar y decorar conjuntos de párrafos con símbolos de prefijo y sangrías.
// Podemos crear listas anidadas aumentando el nivel de sangría. 
// Podemos comenzar y finalizar una lista usando la propiedad "ListFormat" del generador de documentos. 
// Cada párrafo que agreguemos entre el inicio y el final de una lista se convertirá en un elemento de la lista.
// A continuación se muestran dos tipos de listas que podemos crear con un generador de documentos.
// 1 - Una lista con viñetas:
// Esta lista aplicará una sangría y un símbolo de viñeta ("•") antes de cada párrafo.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Great performance");
builder.Writeln("High reliability");
builder.Writeln("Quality code and working");
builder.Writeln("Wide variety of features");
builder.Writeln("Easy to understand API");

// Finaliza la lista con viñetas.
builder.ListFormat.RemoveNumbers();

builder.InsertBreak(BreakType.ParagraphBreak);
builder.Writeln("Aspose.Words allows:");

// 2 - Una lista numerada:
// Las listas numeradas crean un orden lógico para sus párrafos numerando cada elemento.
builder.ListFormat.ApplyNumberDefault();

// Este párrafo es el primer elemento. El primer elemento de una lista numerada tendrá un "1". como su símbolo de elemento de lista.
builder.Writeln("Opening documents from different formats:");

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Llamar al método "ListIndent" para aumentar el nivel de la lista actual,
// que iniciará una nueva lista independiente, con una sangría más profunda, en el elemento actual del primer nivel de la lista.
builder.ListFormat.ListIndent();

Assert.AreEqual(1, builder.ListFormat.ListLevelNumber);

// Estos son los primeros tres elementos de la lista del segundo nivel de la lista, que mantendrán un conteo
// independiente del recuento del primer nivel de lista. De acuerdo con el formato de lista actual,
// tendrán símbolos de "a.", "b.", y "c.".
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");

// Llame al método "ListOutdent" para volver al nivel de lista anterior.
builder.ListFormat.ListOutdent();

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Estos dos párrafos continuarán la cuenta del primer nivel de la lista.
// Estos elementos tendrán los símbolos "2" y "3".
builder.Writeln("Processing documents");
builder.Writeln("Saving documents in different formats:");

// Si aumentamos el nivel de la lista a un nivel al que hemos agregado elementos anteriormente,
// la lista anidada estará separada de la anterior y su numeración comenzará desde el principio. 
// Estos elementos de la lista tendrán los símbolos "a.", "b.", "c.", "d." y "e".
builder.ListFormat.ListIndent();
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");
builder.Writeln("MHTML");
builder.Writeln("Plain text");

// Elimina la sangría del nivel de la lista de nuevo.
builder.ListFormat.ListOutdent();
builder.Writeln("Doing many other things!");

// Finaliza la lista numerada.
builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.ApplyDefaultBulletsAndNumbers.docx");
```

### Ver también

* class [ListFormat](../)
* espacio de nombres [Aspose.Words.Lists](../../listformat/)
* asamblea [Aspose.Words](../../../)


