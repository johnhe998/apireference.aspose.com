---
title: List.Document
second_title: Aspose.Words för .NET API Referens
description: List fast egendom. Hämtar ägardokumentet.
type: docs
weight: 10
url: /sv/net/aspose.words.lists/list/document/
---
## List.Document property

Hämtar ägardokumentet.

```csharp
public DocumentBase Document { get; }
```

### Anmärkningar

En lista har alltid ett överordnat dokument och är endast giltig i sammanhanget för det dokumentet.

### Exempel

Visar hur man verifierar ägardokumentegenskaper för listor.

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

### Se även

* class [DocumentBase](../../../aspose.words/documentbase/)
* class [List](../)
* namnutrymme [Aspose.Words.Lists](../../list/)
* hopsättning [Aspose.Words](../../../)


