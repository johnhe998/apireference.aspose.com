---
title: Enum FindReplaceDirection
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Replacing.FindReplaceDirection enumeración. Especifica la dirección para las operaciones de reemplazo.
type: docs
weight: 4350
url: /es/net/aspose.words.replacing/findreplacedirection/
---
## FindReplaceDirection enumeration

Especifica la dirección para las operaciones de reemplazo.

```csharp
public enum FindReplaceDirection
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Forward | `0` | Los elementos coincidentes se reemplazan del primero al último. |
| Backward | `1` | Los elementos coincidentes se reemplazan del último al primero. |

### Ejemplos

Muestra cómo determinar en qué dirección atraviesa el documento una operación de buscar y reemplazar.

```csharp
public void Direction(FindReplaceDirection findReplaceDirection)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Inserte tres ejecuciones que podamos buscar usando un patrón de expresiones regulares.
    // Coloque una de esas ejecuciones dentro de un cuadro de texto.
    builder.Writeln("Match 1.");
    builder.Writeln("Match 2.");
    builder.Writeln("Match 3.");
    builder.Writeln("Match 4.");

    // Podemos usar un objeto "FindReplaceOptions" para modificar el proceso de buscar y reemplazar.
    FindReplaceOptions options = new FindReplaceOptions();

    // Asigne una devolución de llamada personalizada a la propiedad "ReplaceingCallback".
    TextReplacementRecorder callback = new TextReplacementRecorder();
    options.ReplacingCallback = callback;

    // Establecer la propiedad "Dirección" en "FindReplaceDirection.Backward" para obtener la búsqueda y reemplazo
    // operación para comenzar desde el final del rango y volver al principio.
    // Establecer la propiedad "Dirección" en "FindReplaceDirection.Backward" para obtener la búsqueda y reemplazo
    // operación para comenzar desde el principio del rango y recorrer hasta el final.
    options.Direction = findReplaceDirection;

    doc.Range.Replace(new Regex(@"Match \d*"), "Replacement", options);

    Assert.AreEqual("Replacement.\r" +
                    "Replacement.\r" +
                    "Replacement.\r" +
                    "Replacement.", doc.GetText().Trim());

    switch (findReplaceDirection)
    {
        case FindReplaceDirection.Forward:
            Assert.AreEqual(new[] { "Match 1", "Match 2", "Match 3", "Match 4" }, callback.Matches);
            break;
        case FindReplaceDirection.Backward:
            Assert.AreEqual(new[] { "Match 4", "Match 3", "Match 2", "Match 1" }, callback.Matches);
            break;
    }
}

/// <summary>
/// Registra todas las coincidencias que ocurren durante una operación de buscar y reemplazar en el orden en que ocurren.
/// </summary>
private class TextReplacementRecorder : IReplacingCallback
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

* espacio de nombres [Aspose.Words.Replacing](../../aspose.words.replacing/)
* asamblea [Aspose.Words](../../)


