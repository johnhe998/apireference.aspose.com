---
title: ListCollection.Count
second_title: Aspose.Words für .NET-API-Referenz
description: ListCollection eigendom. Ruft die Anzahl der nummerierten und Aufzählungslisten im Dokument ab.
type: docs
weight: 10
url: /de/net/aspose.words.lists/listcollection/count/
---
## ListCollection.Count property

Ruft die Anzahl der nummerierten und Aufzählungslisten im Dokument ab.

```csharp
public int Count { get; }
```

### Beispiele

Zeigt, wie Eigentümerdokumenteigenschaften von Listen überprüft werden.

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

### Siehe auch

* class [ListCollection](../)
* namensraum [Aspose.Words.Lists](../../listcollection/)
* Montage [Aspose.Words](../../../)


