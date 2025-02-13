---
title: ListLabel.LabelString
second_title: Referencia de API de Aspose.Words para .NET
description: ListLabel propiedad. Obtiene una representación de cadena de la etiqueta de la lista.
type: docs
weight: 20
url: /es/net/aspose.words.lists/listlabel/labelstring/
---
## ListLabel.LabelString property

Obtiene una representación de cadena de la etiqueta de la lista.

```csharp
public string LabelString { get; }
```

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

* class [ListLabel](../)
* espacio de nombres [Aspose.Words.Lists](../../listlabel/)
* asamblea [Aspose.Words](../../../)


