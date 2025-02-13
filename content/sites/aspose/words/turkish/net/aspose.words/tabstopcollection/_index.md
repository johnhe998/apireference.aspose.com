---
title: Class TabStopCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.TabStopCollection sınıf. Bir koleksiyonTabStopbir paragraf veya stil için özel sekmeleri temsil eden nesneler.
type: docs
weight: 5910
url: /tr/net/aspose.words/tabstopcollection/
---
## TabStopCollection class

Bir koleksiyon[`TabStop`](../tabstop/)bir paragraf veya stil için özel sekmeleri temsil eden nesneler.

```csharp
public class TabStopCollection : InternableComplexAttr
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words/tabstopcollection/count/) { get; } | Koleksiyondaki sekme duraklarının sayısını alır. |
| [Item](../../aspose.words/tabstopcollection/item/) { get; } | Verilen dizinde bir sekme durağı alır. (2 indexers) |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words/tabstopcollection/add/#add)(TabStop) | Koleksiyonda bir sekme durağı ekler veya onun yerini alır. |
| [Add](../../aspose.words/tabstopcollection/add/#add_1)(double, TabAlignment, TabLeader) | Koleksiyonda bir sekme durağı ekler veya onun yerini alır. |
| [After](../../aspose.words/tabstopcollection/after/)(double) | Belirtilen konumun sağındaki ilk sekme durağını alır. |
| [Before](../../aspose.words/tabstopcollection/before/)(double) | Belirtilen konumun solundaki ilk sekme durağını alır. |
| [Clear](../../aspose.words/tabstopcollection/clear/)() | Tüm sekme durağı konumlarını siler. |
| override [Equals](../../aspose.words/tabstopcollection/equals/#equals_1)(object) | Belirtilen nesnenin değer olarak geçerli nesneye eşit olup olmadığını belirler. |
| [Equals](../../aspose.words/tabstopcollection/equals/#equals)(TabStopCollection) | Belirtilen TabStopCollection değerinin geçerli TabStopCollection değerine eşit olup olmadığını belirler. |
| override [GetHashCode](../../aspose.words/tabstopcollection/gethashcode/)() | Bu tür için bir karma işlevi olarak hizmet eder. |
| [GetIndexByPosition](../../aspose.words/tabstopcollection/getindexbyposition/)(double) | Belirtilen konumdaki bir sekme durağının dizinini alır. |
| [GetPositionByIndex](../../aspose.words/tabstopcollection/getpositionbyindex/)(int) | Belirtilen dizindeki sekme durağının konumunu (nokta olarak) alır. |
| [RemoveByIndex](../../aspose.words/tabstopcollection/removebyindex/)(int) | Belirtilen dizindeki bir sekme durağını koleksiyondan kaldırır. |
| [RemoveByPosition](../../aspose.words/tabstopcollection/removebyposition/)(double) | Belirtilen konumdaki bir sekme durağını koleksiyondan kaldırır. |

### Notlar

Microsoft Word belgelerinde, bir paragraf stilinin özelliklerinde veya doğrudan bir paragrafın özelliklerinde bir sekme durağı tanımlanabilir. Bir stil, başka bir stili temel alabilir. Bu nedenle, belirli bir nesne için tam sekme durakları kümesi, doğrudan bu nesne üzerinde tanımlanan sekme durakları ile üst stillerden devralınan sekme duraklarının birleşimidir.

Aspose.Words'de, bir **Sekme Durakları** bir paragraf veya stil için koleksiyon, yalnızca doğrudan bu paragraf veya stil için tanımlanmış özel sekme duraklarını içerir. Koleksiyon, üst stillerde tanımlanan sekme duraklarını veya varsayılan sekme duraklarını içermez.

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

* class [InternableComplexAttr](../internablecomplexattr/)
* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


