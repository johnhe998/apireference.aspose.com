---
title: RevisionCollection.AcceptAll
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionCollection método. Acepta todas las revisiones de esta colección.
type: docs
weight: 40
url: /es/net/aspose.words/revisioncollection/acceptall/
---
## RevisionCollection.AcceptAll method

Acepta todas las revisiones de esta colección.

```csharp
public void AcceptAll()
```

### Ejemplos

Muestra cómo comparar documentos.

```csharp
Document docOriginal = new Document();
DocumentBuilder builder = new DocumentBuilder(docOriginal);
builder.Writeln("This is the original document.");

Document docEdited = new Document();
builder = new DocumentBuilder(docEdited);
builder.Writeln("This is the edited document.");

// La comparación de documentos con revisiones generará una excepción.
if (docOriginal.Revisions.Count == 0 && docEdited.Revisions.Count == 0)
    docOriginal.Compare(docEdited, "authorName", DateTime.Now);

// Después de la comparación, el documento original obtendrá una nueva revisión
// por cada elemento que sea diferente en el documento editado.
{
    Console.WriteLine($"Revision type: {r.RevisionType}, on a node of type \"{r.ParentNode.NodeType}\"");
    Console.WriteLine($"\tChanged text: \"{r.ParentNode.GetText()}\"");
}

// Aceptar estas revisiones transformará el documento original en el documento editado.
docOriginal.Revisions.AcceptAll();

Assert.AreEqual(docOriginal.GetText(), docEdited.GetText());
```

### Ver también

* class [RevisionCollection](../)
* espacio de nombres [Aspose.Words](../../revisioncollection/)
* asamblea [Aspose.Words](../../../)


