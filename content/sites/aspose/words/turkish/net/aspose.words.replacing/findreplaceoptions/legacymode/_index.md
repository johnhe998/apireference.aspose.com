---
title: FindReplaceOptions.LegacyMode
second_title: Aspose.Words for .NET API Referansı
description: FindReplaceOptions mülk. Eski bul/değiştir algoritmasının kullanıldığını gösteren bir boole değeri alır veya ayarlar.
type: docs
weight: 110
url: /tr/net/aspose.words.replacing/findreplaceoptions/legacymode/
---
## FindReplaceOptions.LegacyMode property

Eski bul/değiştir algoritmasının kullanıldığını gösteren bir boole değeri alır veya ayarlar.

```csharp
public bool LegacyMode { get; set; }
```

### Notlar

Gelişmiş bul/değiştir özelliği tanıtılmadan önceki davranışın tam olarak aynısına ihtiyacınız varsa bu bayrağı kullanın. Eski algoritmanın aralarla değiştirme, biçimlendirme uygulama vb. gibi gelişmiş özellikleri desteklemediğini unutmayın.

### Örnekler

Değiştirme kalıplarında yer değiştirmelerin nasıl tanınacağını ve kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Jason gave money to Paul.");

Regex regex = new Regex(@"([A-z]+) gave money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions();
options.UseSubstitutions = true;

// Eski modu kullanmak pek çok gelişmiş özelliği desteklemez, bu yüzden onu 'false' olarak ayarlamamız gerekiyor.
options.LegacyMode = false;

doc.Range.Replace(regex, @"$2 took money from $1", options);

Assert.AreEqual(doc.GetText(), "Paul took money from Jason.\f");
```

### Ayrıca bakınız

* class [FindReplaceOptions](../)
* ad alanı [Aspose.Words.Replacing](../../findreplaceoptions/)
* toplantı [Aspose.Words](../../../)


