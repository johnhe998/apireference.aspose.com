---
title: HtmlFixedSaveOptions.OptimizeOutput
second_title: Aspose.Words for .NET API Referansı
description: HtmlFixedSaveOptions mülk. Bayrak çıktının optimize edilmesinin gerekip gerekmediğini gösterir. Bu bayrak ayarlanırsa fazladan iç içe tuvaller ve boş tuvaller kaldırılırsa aynı biçimlendirmeye sahip komşu glifler de birleştirilir. Not Aşağıdaki durumlarda içerik görüntüsünün doğruluğu etkilenebilir bu özellik true olarak ayarlanmıştır. Varsayılan değer true.
type: docs
weight: 100
url: /tr/net/aspose.words.saving/htmlfixedsaveoptions/optimizeoutput/
---
## HtmlFixedSaveOptions.OptimizeOutput property

Bayrak, çıktının optimize edilmesinin gerekip gerekmediğini gösterir. Bu bayrak ayarlanırsa, fazladan iç içe tuvaller ve boş tuvaller kaldırılırsa, aynı biçimlendirmeye sahip komşu glifler de birleştirilir. Not: Aşağıdaki durumlarda içerik görüntüsünün doğruluğu etkilenebilir: bu özellik true olarak ayarlanmıştır. Varsayılan değer true.

```csharp
public override bool OptimizeOutput { get; set; }
```

### Örnekler

Çeşitli gereksiz nesneleri kaldırarak bir belgeyi HTML'ye kaydederken nasıl basitleştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { OptimizeOutput = optimizeOutput };

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html", saveOptions);

// Belgenin optimize edilmiş sürümünün boyutu, optimize edilmemiş belgenin boyutunun neredeyse üçte biri kadardır.
Assert.AreEqual(optimizeOutput ? 62521 : 191770,
    new FileInfo(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html").Length, 200);
```

### Ayrıca bakınız

* class [HtmlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


