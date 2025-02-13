---
title: Paragraph.JoinRunsWithSameFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: Paragraph método. Une ejecuciones con el mismo formato en el párrafo.
type: docs
weight: 280
url: /es/net/aspose.words/paragraph/joinrunswithsameformatting/
---
## Paragraph.JoinRunsWithSameFormatting method

Une ejecuciones con el mismo formato en el párrafo.

```csharp
public int JoinRunsWithSameFormatting()
```

### Valor_devuelto

Número de uniones realizadas. Cuando **norte** se están uniendo tramos adyacentes, cuentan como **n-1** Uniones.

### Ejemplos

Muestra cómo simplificar párrafos fusionando tiradas superfluas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta cuatro tiradas de texto en el párrafo.
builder.Write("Run 1. ");
builder.Write("Run 2. ");
builder.Write("Run 3. ");
builder.Write("Run 4. ");

// Si abrimos este documento en Microsoft Word, el párrafo se verá como un cuerpo de texto continuo.
// Sin embargo, constará de cuatro ejecuciones separadas con el mismo formato. Párrafos fragmentados como este
// puede ocurrir cuando editamos manualmente partes de un párrafo muchas veces en Microsoft Word.
Paragraph para = builder.CurrentParagraph;

Assert.AreEqual(4, para.Runs.Count);

// Cambia el estilo de la última ejecución para diferenciarla de las tres primeras.
para.Runs[3].Font.StyleIdentifier = StyleIdentifier.Emphasis;

// Podemos ejecutar el método "JoinRunsWithSameFormatting" para optimizar el contenido del documento
// fusionando ejecuciones similares en una, reduciendo su recuento general.
// Este método también devuelve el número de ejecuciones que este método fusionó.
// Estas dos fusiones se produjeron para combinar las Ejecuciones n.° 1, n.° 2 y n.° 3,
// mientras omite la Ejecución #4 porque tiene un estilo incompatible.
Assert.AreEqual(2, para.JoinRunsWithSameFormatting());

// El número de ejecuciones restantes será igual al recuento original
// menos el número de fusiones de ejecución que realizó el método "JoinRunsWithSameFormatting".
Assert.AreEqual(2, para.Runs.Count);
Assert.AreEqual("Run 1. Run 2. Run 3. ", para.Runs[0].Text);
Assert.AreEqual("Run 4. ", para.Runs[1].Text);
```

### Ver también

* class [Paragraph](../)
* espacio de nombres [Aspose.Words](../../paragraph/)
* asamblea [Aspose.Words](../../../)


