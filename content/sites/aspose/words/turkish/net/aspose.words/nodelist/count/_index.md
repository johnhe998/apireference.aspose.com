---
title: NodeList.Count
second_title: Aspose.Words for .NET API Referansı
description: NodeList mülk. Listedeki düğüm sayısını alır.
type: docs
weight: 10
url: /tr/net/aspose.words/nodelist/count/
---
## NodeList.Count property

Listedeki düğüm sayısını alır.

```csharp
public int Count { get; }
```

### Örnekler

Bir NodeList'te gezinmek için XPath'lerin nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// DocumentBuilder ile bazı düğümler ekleyin.
builder.Writeln("Hello world!");

builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();

#if NET48 || JAVA
builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
#elif NET5_0_OR_GREATER || __MOBILE__
using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
    builder.InsertImage(image);
#endif

// Belgemiz üç Çalıştırma düğümü içeriyor.
NodeList nodeList = doc.SelectNodes("//Koşmak");

Assert.AreEqual(3, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Hello world!"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Tüm Çalıştırma düğümlerini seçmek için çift eğik çizgi kullanın
// bunlar, eklediğimiz iki hücrenin içindeki çalıştırmalar olan bir Tablo düğümünün dolaylı torunlarıdır.
nodeList = doc.SelectNodes("//Table//Koşmak");

Assert.AreEqual(2, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Tek eğik çizgi, doğrudan alttan gelen ilişkileri belirtir,
// çift eğik çizgi kullandığımızda atladığımız.
Assert.AreEqual(doc.SelectNodes(" //Tablo//Çalıştır"),
    doc.SelectNodes("//Tablo/Satır/Hücre/Paragraf/Çalıştır"));

// Eklediğimiz resmi içeren şekle erişin.
nodeList = doc.SelectNodes("//Şekil");

Assert.AreEqual(1, nodeList.Count);

Shape shape = (Shape)nodeList[0];
Assert.True(shape.HasImage);
```

### Ayrıca bakınız

* class [NodeList](../)
* ad alanı [Aspose.Words](../../nodelist/)
* toplantı [Aspose.Words](../../../)


