---
title: ListCollection.Count
second_title: Referencia de API de Aspose.Words para .NET
description: ListCollection propiedad. Obtiene el recuento de listas numeradas y con viñetas en el documento.
type: docs
weight: 10
url: /es/net/aspose.words.lists/listcollection/count/
---
## ListCollection.Count property

Obtiene el recuento de listas numeradas y con viñetas en el documento.

```csharp
public int Count { get; }
```

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

### Ver también

* class [ListCollection](../)
* espacio de nombres [Aspose.Words.Lists](../../listcollection/)
* asamblea [Aspose.Words](../../../)


