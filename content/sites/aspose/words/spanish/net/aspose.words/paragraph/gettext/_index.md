---
title: Paragraph.GetText
second_title: Referencia de API de Aspose.Words para .NET
description: Paragraph método. Obtiene el texto de este párrafo incluido el carácter de fin de párrafo.
type: docs
weight: 260
url: /es/net/aspose.words/paragraph/gettext/
---
## Paragraph.GetText method

Obtiene el texto de este párrafo, incluido el carácter de fin de párrafo.

```csharp
public override string GetText()
```

### Observaciones

El texto de todos los nodos secundarios se concatena y el carácter de final de párrafo se agrega de la siguiente manera:

* Si el párrafo es el último párrafo de[`Body`](../../body/) , entonces [`ControlChar.SectionBreak`](../../controlchar/sectionbreak/) (\x000c) se adjunta.
* Si el párrafo es el último párrafo de[`Cell`](../../../aspose.words.tables/cell/) , entonces [`ControlChar.Célula`](../../controlchar/cell/) (\x0007) se adjunta.
* Para todos los demás párrafos [`ControlChar.ParagraphBreak`](../../controlchar/paragraphbreak/) (\r) se adjunta.

La cadena devuelta incluye todos los caracteres especiales y de control como se describe en[`ControlChar`](../../controlchar/).

### Ejemplos

Muestra cómo agregar, actualizar y eliminar nodos secundarios en la colección de elementos secundarios de CompositeNode.

```csharp
Document doc = new Document();

// Un documento vacío, por defecto, tiene un párrafo.
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// Los nodos compuestos como nuestro párrafo pueden contener otros nodos compuestos y en línea como elementos secundarios.
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Run paragraphText = new Run(doc, "Initial text. ");
paragraph.AppendChild(paragraphText);

// Crea tres nodos de ejecución más.
Run run1 = new Run(doc, "Run 1. ");
Run run2 = new Run(doc, "Run 2. ");
Run run3 = new Run(doc, "Run 3. ");

// El cuerpo del documento no mostrará estas ejecuciones hasta que las insertemos en un nodo compuesto
// eso en sí mismo es parte del árbol de nodos del documento, como hicimos con la primera ejecución.
// Podemos determinar donde esta el contenido de texto de los nodos que insertamos
// aparece en el documento especificando una ubicación de inserción relativa a otro nodo en el párrafo.
Assert.AreEqual("Initial text.", paragraph.GetText().Trim());

// Inserta la segunda ejecución en el párrafo delante de la ejecución inicial.
paragraph.InsertBefore(run2, paragraphText);

Assert.AreEqual("Run 2. Initial text.", paragraph.GetText().Trim());

// Inserta la tercera ejecución después de la ejecución inicial.
paragraph.InsertAfter(run3, paragraphText);

Assert.AreEqual("Run 2. Initial text. Run 3.", paragraph.GetText().Trim());

// Inserta la primera ejecución al comienzo de la colección de nodos secundarios del párrafo.
paragraph.PrependChild(run1);

Assert.AreEqual("Run 1. Run 2. Initial text. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(4, paragraph.GetChildNodes(NodeType.Any, true).Count);

// Podemos modificar el contenido de la ejecución editando y eliminando los nodos secundarios existentes.
((Run)paragraph.GetChildNodes(NodeType.Run, true)[1]).Text = "Updated run 2. ";
paragraph.GetChildNodes(NodeType.Run, true).Remove(paragraphText);

Assert.AreEqual("Run 1. Updated run 2. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(3, paragraph.GetChildNodes(NodeType.Any, true).Count);
```

### Ver también

* class [Paragraph](../)
* espacio de nombres [Aspose.Words](../../paragraph/)
* asamblea [Aspose.Words](../../../)


