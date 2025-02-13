---
title: ListCollection.GetListByListId
second_title: Aspose.Words for .NET API Referansı
description: ListCollection yöntem. Liste tanımlayıcısına göre bir liste alır.
type: docs
weight: 70
url: /tr/net/aspose.words.lists/listcollection/getlistbylistid/
---
## ListCollection.GetListByListId method

Liste tanımlayıcısına göre bir liste alır.

```csharp
public List GetListByListId(int listId)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| listId | Int32 | Liste tanımlayıcısı. |

### Geri dönüş değeri

Liste nesnesini döndürür. Belirtilen tanımlayıcıya sahip bir liste bulunamazsa null döndürür.

### Notlar

Normalde bu yöntemi kullanmanıza gerek yoktur. Çoğu zaman, liste formatting öğesini paragraflara yalnızca[`List`](../../listformat/list/) property [`ListFormat`](../../listformat/) nesne.

### Örnekler

Listelerin sahip belge özelliklerinin nasıl doğrulanacağını gösterir.

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

### Ayrıca bakınız

* class [List](../../list/)
* class [ListCollection](../)
* ad alanı [Aspose.Words.Lists](../../listcollection/)
* toplantı [Aspose.Words](../../../)


