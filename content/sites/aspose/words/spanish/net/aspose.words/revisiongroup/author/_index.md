---
title: RevisionGroup.Author
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionGroup propiedad. Obtiene el autor de este grupo de revisión.
type: docs
weight: 10
url: /es/net/aspose.words/revisiongroup/author/
---
## RevisionGroup.Author property

Obtiene el autor de este grupo de revisión.

```csharp
public string Author { get; }
```

### Ejemplos

Muestra cómo imprimir información sobre un grupo de revisiones en un documento.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Ver también

* class [RevisionGroup](../)
* espacio de nombres [Aspose.Words](../../revisiongroup/)
* asamblea [Aspose.Words](../../../)


