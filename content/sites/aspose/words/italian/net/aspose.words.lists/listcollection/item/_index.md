---
title: ListCollection.Item
second_title: Aspose.Words per .NET API Reference
description: ListCollection proprietà. Ottiene un elenco per indice.
type: docs
weight: 30
url: /it/net/aspose.words.lists/listcollection/item/
---
## ListCollection indexer

Ottiene un elenco per indice.

```csharp
public List this[int index] { get; }
```

### Esempi

Mostra come verificare le proprietà del documento proprietario degli elenchi.

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

Mostra come applicare la formattazione dell'elenco di un elenco esistente a una raccolta di paragrafi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Write("Paragraph 3");

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

Assert.AreEqual(0, paras.Count(n => (n as Paragraph).ListFormat.IsListItem));

doc.Lists.Add(ListTemplate.NumberDefault);
List list = doc.Lists[0];

foreach (Paragraph paragraph in paras.OfType<Paragraph>())
{
    paragraph.ListFormat.List = list;
    paragraph.ListFormat.ListLevelNumber = 2;
}

Assert.AreEqual(3, paras.Count(n => (n as Paragraph).ListFormat.IsListItem));
```

### Guarda anche

* class [List](../../list/)
* class [ListCollection](../)
* spazio dei nomi [Aspose.Words.Lists](../../listcollection/)
* assemblea [Aspose.Words](../../../)


