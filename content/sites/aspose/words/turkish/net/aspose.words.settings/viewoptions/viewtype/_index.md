---
title: ViewOptions.ViewType
second_title: Aspose.Words for .NET API Referansı
description: ViewOptions mülk. Microsoft Wordde görüntüleme modunu kontrol eder.
type: docs
weight: 40
url: /tr/net/aspose.words.settings/viewoptions/viewtype/
---
## ViewOptions.ViewType property

Microsoft Word'de görüntüleme modunu kontrol eder.

```csharp
public ViewType ViewType { get; set; }
```

### Notlar

Aspose.Words bu seçeneği okuyup yazabiliyor olsa da, kullanımı uygulamaya özeldir. Örneğin MS Word 2013, bu seçeneğin değerine uymaz.

### Örnekler

Microsoft Word'ün eski sürümlerinin yükleme sırasında bir belgeye uygulanacağı özel bir yakınlaştırma faktörünün nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

### Ayrıca bakınız

* enum [ViewType](../../viewtype/)
* class [ViewOptions](../)
* ad alanı [Aspose.Words.Settings](../../viewoptions/)
* toplantı [Aspose.Words](../../../)


