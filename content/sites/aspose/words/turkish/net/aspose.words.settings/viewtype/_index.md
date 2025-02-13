---
title: Enum ViewType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Settings.ViewType Sıralama. Microsoft Wordde görüntüleme modu için olası değerler.
type: docs
weight: 5660
url: /tr/net/aspose.words.settings/viewtype/
---
## ViewType enumeration

Microsoft Word'de görüntüleme modu için olası değerler.

```csharp
public enum ViewType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Belge, uygulamanın varsayılan görünümünde işlenecektir. |
| Reading | `0` | Belge, uygulamanın varsayılan görünümünde işlenecektir. |
| PageLayout | `1` | Belge, belgeyi yazdırılacağı gibi görüntüleyen bir görünümde açılacaktır. |
| Outline | `3` | Belge, ana hatlar oluşturmak veya uzun belgeler oluşturmak için optimize edilmiş bir görünümde işlenecektir. |
| Normal | `4` | Belge, ana hatlar oluşturmak veya uzun belgeler oluşturmak için optimize edilmiş bir görünümde işlenecektir. |
| Web | `5` | Belge, bu belgenin bir web sayfasında görüntülenme şeklini taklit eden bir görünümde oluşturulacaktır. |

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

* class [ViewOptions](../viewoptions/)
* property [ViewType](../viewoptions/viewtype/)
* ad alanı [Aspose.Words.Settings](../../aspose.words.settings/)
* toplantı [Aspose.Words](../../)


