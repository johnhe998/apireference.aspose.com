---
title: FindReplaceOptions.UseLegacyOrder
second_title: Referencia de API de Aspose.Words para .NET
description: FindReplaceOptions propiedad. True indica que una búsqueda de texto se realiza secuencialmente de arriba a abajo considerando los cuadros de texto. El valor por defecto es false.
type: docs
weight: 150
url: /es/net/aspose.words.replacing/findreplaceoptions/uselegacyorder/
---
## FindReplaceOptions.UseLegacyOrder property

True indica que una búsqueda de texto se realiza secuencialmente de arriba a abajo considerando los cuadros de texto. El valor por defecto es false.

```csharp
public bool UseLegacyOrder { get; set; }
```

### Ejemplos

Muestra cómo cambiar el orden de búsqueda de los nodos al realizar una operación de buscar y reemplazar texto.

```csharp
[TestCase(true)] // ExSaltar
[TestCase(false)] // ExSaltar
public void UseLegacyOrder(bool useLegacyOrder)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Inserte tres ejecuciones que podamos buscar usando un patrón de expresiones regulares.
    // Coloque una de esas ejecuciones dentro de un cuadro de texto.
    builder.Writeln("[tag 1]");
    Shape textBox = builder.InsertShape(ShapeType.TextBox, 100, 50);
    builder.Writeln("[tag 2]");
    builder.MoveTo(textBox.FirstParagraph);
    builder.Write("[tag 3]");

    // Podemos usar un objeto "FindReplaceOptions" para modificar el proceso de buscar y reemplazar.
    FindReplaceOptions options = new FindReplaceOptions();

    // Asigne una devolución de llamada personalizada a la propiedad "ReplaceingCallback".
    TextReplacementTracker callback = new TextReplacementTracker();
    options.ReplacingCallback = callback;

    // Si establecemos la propiedad "UseLegacyOrder" en "true", el
    // la operación de buscar y reemplazar pasará por todas las ejecuciones fuera de un cuadro de texto
    // antes de pasar por los que están dentro de un cuadro de texto.
    // Si establecemos la propiedad "UseLegacyOrder" en "falso", el
    // La operación de buscar y reemplazar repasará todas las ejecuciones en un rango en orden secuencial.
    options.UseLegacyOrder = useLegacyOrder;

    doc.Range.Replace(new Regex(@"\[tag \d*\]"), "", options);

    Assert.AreEqual(useLegacyOrder ?
        new List<string> { "[tag 1]", "[tag 3]", "[tag 2]" } :
        new List<string> { "[tag 1]", "[tag 2]", "[tag 3]" }, callback.Matches);
}

/// <summary>
/// Registra el orden de todas las coincidencias que ocurren durante una operación de buscar y reemplazar.
/// </summary>
private class TextReplacementTracker : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs e)
    {
        Matches.Add(e.Match.Value);
        return ReplaceAction.Replace;
    }

    public List<string> Matches { get; } = new List<string>();
}
```

### Ver también

* class [FindReplaceOptions](../)
* espacio de nombres [Aspose.Words.Replacing](../../findreplaceoptions/)
* asamblea [Aspose.Words](../../../)


