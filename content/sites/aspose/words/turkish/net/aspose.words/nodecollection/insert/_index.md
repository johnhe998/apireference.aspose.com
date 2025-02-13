---
title: NodeCollection.Insert
second_title: Aspose.Words for .NET API Referansı
description: NodeCollection yöntem. Belirtilen dizindeki koleksiyona bir düğüm ekler.
type: docs
weight: 80
url: /tr/net/aspose.words/nodecollection/insert/
---
## NodeCollection.Insert method

Belirtilen dizindeki koleksiyona bir düğüm ekler.

```csharp
public void Insert(int index, Node node)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| index | Int32 | Düğümün sıfır tabanlı dizini. Negatif dizinlere izin verilir ve listenin arkasından erişimi gösterir. Örneğin -1 son düğüm anlamına gelir, -2 sondan önceki ikinci anlamına gelir vb. |
| node | Node | Eklenecek düğüm. |

### istisnalar

| istisna | şart |
| --- | --- |
| NotSupportedException | bu **Düğüm Koleksiyonu** "derin" bir koleksiyondur. |

### Notlar

Düğüm, koleksiyonun oluşturulduğu düğüm nesnesine alt öğe olarak eklenir.

Dizin Sayıya eşit veya daha büyükse, düğüm koleksiyonun sonuna eklenir.

İndeks negatifse ve mutlak değeri Count'tan büyükse, düğüm koleksiyonun sonuna eklenir.

newChild zaten ağaçtaysa, önce kaldırılır.

Eklenen düğüm başka bir belgeden oluşturulmuşsa, kullanmanız gerekir.[`ImportNode`](../../documentbase/importnode/) düğümü geçerli belgeye aktarmak için. Alınan düğüm daha sonra geçerli belgeye eklenebilir.

### Örnekler

NodeCollection ile nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// DocumentBuilder kullanarak Çalıştırmalar ekleyerek belgeye metin ekleyin.
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// "Write" yönteminin her çağrısı yeni bir Run oluşturur,
// daha sonra üst Paragrafın RunCollection'ında görünür.
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// RunCollection'a manuel olarak da bir düğüm ekleyebiliriz.
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// Tek tek çalıştırmalara erişin ve metinlerini belgeden kaldırmak için bunları kaldırın.
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### Ayrıca bakınız

* class [Node](../../node/)
* class [NodeCollection](../)
* ad alanı [Aspose.Words](../../nodecollection/)
* toplantı [Aspose.Words](../../../)


