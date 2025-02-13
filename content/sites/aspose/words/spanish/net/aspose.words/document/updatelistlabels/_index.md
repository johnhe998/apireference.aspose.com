---
title: Document.UpdateListLabels
second_title: Referencia de API de Aspose.Words para .NET
description: Document método. Actualiza las etiquetas de la lista para todos los elementos de la lista en el documento.
type: docs
weight: 740
url: /es/net/aspose.words/document/updatelistlabels/
---
## Document.UpdateListLabels method

Actualiza las etiquetas de la lista para todos los elementos de la lista en el documento.

```csharp
public void UpdateListLabels()
```

### Observaciones

Este método actualiza las propiedades de la etiqueta de la lista, como[`LabelValue`](../../../aspose.words.lists/listlabel/labelvalue/) y [`LabelString`](../../../aspose.words.lists/listlabel/labelstring/)para cada[`ListLabel`](../../paragraph/listlabel/) objeto en el documento.

Además, este método a veces se llama implícitamente cuando se actualizan campos en el documento. Esto es requerido porque algunos campos que pueden hacer referencia a números de lista (como TOC o REF) necesitan que estén actualizados.

### Ejemplos

Muestra cómo extraer las etiquetas de lista de todos los párrafos que son elementos de lista.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// Encuentra si tenemos la lista de párrafos. En nuestro documento, nuestra lista usa números arábigos simples,
// que comienzan a las tres y terminan a las seis.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // Este es el texto que obtenemos cuando enviamos este nodo a formato de texto.
    // Esta salida de texto omitirá las etiquetas de lista. Recorte cualquier carácter de formato de párrafo. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // Esto obtiene la posición del párrafo en el nivel actual de la lista. Si tenemos una lista con múltiples niveles,
    // esto nos dirá en qué posición está en ese nivel.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // Combinarlos para incluir la etiqueta de la lista con el texto en la salida.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### Ver también

* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


