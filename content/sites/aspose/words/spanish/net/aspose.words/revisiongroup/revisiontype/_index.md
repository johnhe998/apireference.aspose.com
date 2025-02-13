---
title: RevisionGroup.RevisionType
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionGroup propiedad. Obtiene el tipo de revisiones incluidas en este grupo.
type: docs
weight: 20
url: /es/net/aspose.words/revisiongroup/revisiontype/
---
## RevisionGroup.RevisionType property

Obtiene el tipo de revisiones incluidas en este grupo.

```csharp
public RevisionType RevisionType { get; }
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

* enum [RevisionType](../../revisiontype/)
* class [RevisionGroup](../)
* espacio de nombres [Aspose.Words](../../revisiongroup/)
* asamblea [Aspose.Words](../../../)


