---
title: RevisionGroup.Text
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionGroup propiedad. Devuelve texto insertado/eliminado/movido o descripción del cambio de formato.
type: docs
weight: 30
url: /es/net/aspose.words/revisiongroup/text/
---
## RevisionGroup.Text property

Devuelve texto insertado/eliminado/movido o descripción del cambio de formato.

```csharp
public string Text { get; }
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


