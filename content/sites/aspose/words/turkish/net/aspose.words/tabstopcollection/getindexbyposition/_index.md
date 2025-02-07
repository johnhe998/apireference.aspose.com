---
title: TabStopCollection.GetIndexByPosition
second_title: Aspose.Words for .NET API Referansı
description: TabStopCollection yöntem. Belirtilen konumdaki bir sekme durağının dizinini alır.
type: docs
weight: 90
url: /tr/net/aspose.words/tabstopcollection/getindexbyposition/
---
## TabStopCollection.GetIndexByPosition method

Belirtilen konumdaki bir sekme durağının dizinini alır.

```csharp
public int GetIndexByPosition(double position)
```

### Örnekler

Orada bir sekme durağı olup olmadığını görmek ve dizinini almak için bir konumun nasıl aranacağını gösterir.

```csharp
Document doc = new Document();
TabStopCollection tabStops = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.TabStops;

// 30 mm'lik bir konuma bir sekme durağı ekleyin.
tabStops.Add(ConvertUtil.MillimeterToPoint(30), TabAlignment.Left, TabLeader.Dashes);

// "GetIndexByPosition" tarafından döndürülen "0" sonucu, bir sekme durağının olduğunu doğrular
// 30 mm'de bu koleksiyonda var ve 0 dizininde.
Assert.AreEqual(0, tabStops.GetIndexByPosition(ConvertUtil.MillimeterToPoint(30)));

// "GetIndexByPosition" tarafından döndürülen bir "-1" bunu doğrular
// 60mm pozisyonlu bu koleksiyonda sekme durağı yok.
Assert.AreEqual(-1, tabStops.GetIndexByPosition(ConvertUtil.MillimeterToPoint(60)));
```

### Ayrıca bakınız

* class [TabStopCollection](../)
* ad alanı [Aspose.Words](../../tabstopcollection/)
* toplantı [Aspose.Words](../../../)


