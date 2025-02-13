---
title: NodeList.ToArray
second_title: Aspose.Words for .NET API Referansı
description: NodeList yöntem. Koleksiyondaki tüm düğümleri yeni bir düğüm dizisine kopyalar.
type: docs
weight: 40
url: /tr/net/aspose.words/nodelist/toarray/
---
## NodeList.ToArray method

Koleksiyondaki tüm düğümleri yeni bir düğüm dizisine kopyalar.

```csharp
public Node[] ToArray()
```

### Geri dönüş değeri

Bir dizi düğüm.

### Notlar

Yineleyiciyi geçersiz kıldığı ve canlı koleksiyonlar için yenilemeler gerektirdiğinden, düğüm koleksiyonu üzerinde yineleme yaparken düğüm ekleme/çıkarma yapmamalısınız.

Yineleme sırasında düğüm ekleyebilmek/kaldırabilmek için, düğümlerini sabit boyutlu bir diziye kopyalamak için bu yöntemi kullanın ve ardından dizi üzerinde yineleme yapın.

### Örnekler

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

* class [Node](../../node/)
* class [NodeList](../)
* ad alanı [Aspose.Words](../../nodelist/)
* toplantı [Aspose.Words](../../../)


