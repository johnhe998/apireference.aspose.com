---
title: TabStopCollection.Before
second_title: Aspose.Words for .NET API Referansı
description: TabStopCollection yöntem. Belirtilen konumun solundaki ilk sekme durağını alır.
type: docs
weight: 50
url: /tr/net/aspose.words/tabstopcollection/before/
---
## TabStopCollection.Before method

Belirtilen konumun solundaki ilk sekme durağını alır.

```csharp
public TabStop Before(double position)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| position | Double | Referans konumu (nokta olarak). |

### Geri dönüş değeri

Bir sekme durağı nesnesi veya uygun bir sekme durağı bulunamazsa boş.

### Notlar

ile sekme duraklarını atlar **hizalama** ayarlanır`TabAlignment.Bar`.

### Örnekler

Bir belgenin sekme durakları koleksiyonuyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 nokta, Microsoft Word sekmesi durdurma cetvelinde bir "inç"tir.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// Her "sekme" karakteri, oluşturucunun imlecini bir sonraki sekme durağının konumuna götürür.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// Her paragraf, değerlerini belge oluşturucunun sekme durağı koleksiyonundan kopyalayan sekme durağı koleksiyonunu alır.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// Bir sekme durağı koleksiyonu bizi belirli konumlardan önce ve sonra TabStop'lara yönlendirebilir.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// Varsayılan sekme davranışına geri dönmek için bir paragrafın sekme durağı koleksiyonunu temizleyebiliriz.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### Ayrıca bakınız

* class [TabStop](../../tabstop/)
* class [TabStopCollection](../)
* ad alanı [Aspose.Words](../../tabstopcollection/)
* toplantı [Aspose.Words](../../../)


