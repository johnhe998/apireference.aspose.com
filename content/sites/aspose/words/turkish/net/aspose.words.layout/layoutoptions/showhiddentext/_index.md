---
title: LayoutOptions.ShowHiddenText
second_title: Aspose.Words for .NET API Referansı
description: LayoutOptions mülk. Belgedeki gizli metnin işlenip işlenmediğinin göstergesini alır veya ayarlar. Varsayılan Yanlıştır.
type: docs
weight: 70
url: /tr/net/aspose.words.layout/layoutoptions/showhiddentext/
---
## LayoutOptions.ShowHiddenText property

Belgedeki gizli metnin işlenip işlenmediğinin göstergesini alır veya ayarlar. Varsayılan Yanlış'tır.

```csharp
public bool ShowHiddenText { get; set; }
```

### Notlar

Bu özellik, yalnızca metni değil, tüm gizli içeriği etkiler.

### Örnekler

İşlenmiş bir çıktı belgesindeki metnin nasıl gizleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Gizli metni ekleyin, ardından onu işlenmiş bir belgeden çıkarmak isteyip istemediğimizi belirtin.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

### Ayrıca bakınız

* class [LayoutOptions](../)
* ad alanı [Aspose.Words.Layout](../../layoutoptions/)
* toplantı [Aspose.Words](../../../)


