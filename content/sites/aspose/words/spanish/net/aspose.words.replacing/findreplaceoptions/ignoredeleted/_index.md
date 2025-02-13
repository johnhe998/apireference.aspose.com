---
title: FindReplaceOptions.IgnoreDeleted
second_title: Referencia de API de Aspose.Words para .NET
description: FindReplaceOptions propiedad. Obtiene o establece un valor booleano que indica ignorar el texto dentro de eliminar revisiones. El valor predeterminado esfalso .
type: docs
weight: 60
url: /es/net/aspose.words.replacing/findreplaceoptions/ignoredeleted/
---
## FindReplaceOptions.IgnoreDeleted property

Obtiene o establece un valor booleano que indica ignorar el texto dentro de eliminar revisiones. El valor predeterminado es`falso` .

```csharp
public bool IgnoreDeleted { get; set; }
```

### Ejemplos

Muestra cómo incluir o ignorar texto dentro de las revisiones de eliminación durante una operación de buscar y reemplazar.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

// Comience a rastrear las revisiones y elimine el segundo párrafo, lo que creará una revisión de eliminación.
// Ese párrafo persistirá en el documento hasta que aceptemos la revisión de eliminación.
doc.StartTrackRevisions("John Doe", DateTime.Now);
doc.FirstSection.Body.Paragraphs[1].Remove();
doc.StopTrackRevisions();

Assert.True(doc.FirstSection.Body.Paragraphs[1].IsDeleteRevision);

// Podemos usar un objeto "FindReplaceOptions" para modificar el proceso de búsqueda y reemplazo.
FindReplaceOptions options = new FindReplaceOptions();

// Establezca el indicador "IgnoreDeleted" en "true" para obtener la búsqueda y el reemplazo
// operación para ignorar párrafos que son revisiones de borrado.
// Establezca el indicador "IgnoreDeleted" en "falso" para obtener la búsqueda y el reemplazo
// operación para buscar también texto dentro de eliminar revisiones.
options.IgnoreDeleted = ignoreTextInsideDeleteRevisions;

doc.Range.Replace("Hello", "Greetings", options);

Assert.AreEqual(
    ignoreTextInsideDeleteRevisions
        ? "Greetings world!\rHello again!"
        : "Greetings world!\rGreetings again!", doc.GetText().Trim());
```

### Ver también

* class [FindReplaceOptions](../)
* espacio de nombres [Aspose.Words.Replacing](../../findreplaceoptions/)
* asamblea [Aspose.Words](../../../)


