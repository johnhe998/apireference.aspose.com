---
title: List.ListId
second_title: Referencia de API de Aspose.Words para .NET
description: List propiedad. Obtiene el identificador único de la lista.
type: docs
weight: 60
url: /es/net/aspose.words.lists/list/listid/
---
## List.ListId property

Obtiene el identificador único de la lista.

```csharp
public int ListId { get; }
```

### Observaciones

Normalmente no es necesario utilizar esta propiedad. Pero si lo usa, normalmente lo hace junto con el[`GetListByListId`](../../listcollection/getlistbylistid/) método para encontrar una lista a por su identificador.

### Ejemplos

Muestra cómo verificar las propiedades del documento de propietario de las listas.

```csharp
Document doc = new Document();

ListCollection lists = doc.Lists;

Assert.AreEqual(doc, lists.Document);

List list = lists.Add(ListTemplate.BulletDefault);

Assert.AreEqual(doc, list.Document);

Console.WriteLine("Current list count: " + lists.Count);
Console.WriteLine("Is the first document list: " + (lists[0].Equals(list)));
Console.WriteLine("ListId: " + list.ListId);
Console.WriteLine("List is the same by ListId: " + (lists.GetListByListId(1).Equals(list)));
```

Muestra cómo generar todos los párrafos de un documento que son elementos de lista.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Numbered list item 1");
builder.Writeln("Numbered list item 2");
builder.Writeln("Numbered list item 3");
builder.ListFormat.RemoveNumbers();

builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Bulleted list item 1");
builder.Writeln("Bulleted list item 2");
builder.Writeln("Bulleted list item 3");
builder.ListFormat.RemoveNumbers();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{ 
    Console.WriteLine($"This paragraph belongs to list ID# {para.ListFormat.List.ListId}, number style \"{para.ListFormat.ListLevel.NumberStyle}\"");
    Console.WriteLine($"\t\"{para.GetText().Trim()}\"");
}
```

### Ver también

* class [List](../)
* espacio de nombres [Aspose.Words.Lists](../../list/)
* asamblea [Aspose.Words](../../../)


