---
title: ViewOptions.ZoomType
second_title: Aspose.Words for .NET API Referansı
description: ViewOptions mülk. Pencerenin boyutuna göre bir yakınlaştırma değeri alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.settings/viewoptions/zoomtype/
---
## ViewOptions.ZoomType property

Pencerenin boyutuna göre bir yakınlaştırma değeri alır veya ayarlar.

```csharp
public ZoomType ZoomType { get; set; }
```

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

Microsoft Word'ün eski sürümlerinin yükleme sırasında bir belgeye uygulanacağı özel bir yakınlaştırma türünün nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Microsoft Word'ü almak için "ZoomType" özelliğini "ZoomType.PageWidth" olarak ayarlayın
// belgeyi sayfanın genişliğine sığdırmak için otomatik olarak yakınlaştırmak için.
// Microsoft Word'ü almak için "ZoomType" özelliğini "ZoomType.FullPage" olarak ayarlayın
// ilk sayfanın tamamını görünür kılmak için belgeyi otomatik olarak yakınlaştırmak için.
// Microsoft Word'ü almak için "ZoomType" özelliğini "ZoomType.TextFit" olarak ayarlayın
// ilk sayfanın iç metin kenar boşluklarına sığdırmak için belgeyi otomatik olarak yakınlaştırmak için.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Ayrıca bakınız

* enum [ZoomType](../../zoomtype/)
* class [ViewOptions](../)
* ad alanı [Aspose.Words.Settings](../../viewoptions/)
* toplantı [Aspose.Words](../../../)


