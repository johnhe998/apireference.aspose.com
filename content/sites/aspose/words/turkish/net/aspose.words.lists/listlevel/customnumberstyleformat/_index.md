---
title: ListLevel.CustomNumberStyleFormat
second_title: Aspose.Words for .NET API Referansı
description: ListLevel mülk. Bu liste düzeyi için özel sayı stili biçimini alır. Örneğin a ç ĝ ....
type: docs
weight: 20
url: /tr/net/aspose.words.lists/listlevel/customnumberstyleformat/
---
## ListLevel.CustomNumberStyleFormat property

Bu liste düzeyi için özel sayı stili biçimini alır. Örneğin: "a, ç, ĝ, ...".

```csharp
public string CustomNumberStyleFormat { get; }
```

### Örnekler

Özel sayı stiline sahip bir liste biçiminin nasıl alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Liste öğesinin belirtilen dizini için değer alabiliriz.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Ayrıca bakınız

* class [ListLevel](../)
* ad alanı [Aspose.Words.Lists](../../listlevel/)
* toplantı [Aspose.Words](../../../)


