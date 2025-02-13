---
title: CompositeNode.SelectNodes
second_title: Aspose.Words for .NET API Referansı
description: CompositeNode yöntem. XPath ifadesiyle eşleşen düğümlerin listesini seçer.
type: docs
weight: 200
url: /tr/net/aspose.words/compositenode/selectnodes/
---
## CompositeNode.SelectNodes method

XPath ifadesiyle eşleşen düğümlerin listesini seçer.

```csharp
public NodeList SelectNodes(string xpath)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| xpath | String | XPath ifadesi. |

### Geri dönüş değeri

XPath sorgusuyla eşleşen düğümlerin listesi.

### Notlar

Şu anda yalnızca öğe adlarına sahip ifadeler desteklenmektedir. Öznitelik adlarını kullanan Expressions desteklenmez.

### Örnekler

Bir düğümün bir alan içinde olup olmadığını test etmek için bir XPath ifadesinin nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

// Bu XPath ifadesinden elde edilen NodeList, bir alan içinde bulduğumuz tüm düğümleri içerecektir.
// Ancak, yolda iç içe alanlar varsa, FieldStart ve FieldEnd düğümleri listede olabilir.
// Şu anda FieldCode veya FieldResult'un birden çok paragrafa yayıldığı nadir alanlar bulamıyor.
NodeList resultList =
    doc.SelectNodes("//FieldStart/takip eden kardeş::node()[takip eden kardeş::FieldEnd]");

// Belirtilen çalıştırmanın alan içindeki düğümlerden biri olup olmadığını kontrol edin.
Console.WriteLine($"Contents of the first Run node that's part of a field: {resultList.First(n => n.NodeType == NodeType.Run).GetText().Trim()}");
```

Bir XPath ifadesi kullanarak belirli düğümlerin nasıl seçileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Bu ifade tüm paragraf düğümlerini çıkaracak,
// belgedeki herhangi bir tablo düğümünün soyundan gelenler.
NodeList nodeList = doc.SelectNodes("//Tablo//Paragraf");

// Listeyi bir numaralandırıcı ile yineleyin ve tablonun her hücresindeki her paragrafın içeriğini yazdırın.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Bu ifade, belgedeki herhangi bir Gövde düğümünün doğrudan çocukları olan tüm paragrafları seçecektir.
nodeList = doc.SelectNodes("//Gelişme paragrafı");

// Listeyi bir dizi olarak ele alabiliriz.
Assert.AreEqual(4, nodeList.ToArray().Length);

// Yukarıdakiyle aynı ifadenin ilk sonucunu seçmek için SelectSingleNode'u kullanın.
Node node = doc.SelectSingleNode("//Gelişme paragrafı");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Ayrıca bakınız

* class [NodeList](../../nodelist/)
* class [CompositeNode](../)
* ad alanı [Aspose.Words](../../compositenode/)
* toplantı [Aspose.Words](../../../)


