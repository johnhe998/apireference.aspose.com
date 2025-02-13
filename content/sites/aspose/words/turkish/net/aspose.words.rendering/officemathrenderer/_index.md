---
title: Class OfficeMathRenderer
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Rendering.OfficeMathRenderer sınıf. Bir bireyi işlemek için yöntemler sağlarOfficeMath bir raster veya vektör görüntüsüne veya bir Graphics nesnesine.
type: docs
weight: 4300
url: /tr/net/aspose.words.rendering/officemathrenderer/
---
## OfficeMathRenderer class

Bir bireyi işlemek için yöntemler sağlar[`OfficeMath`](../../aspose.words.math/officemath/) bir raster veya vektör görüntüsüne veya bir Graphics nesnesine.

```csharp
public class OfficeMathRenderer : NodeRendererBase
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [OfficeMathRenderer](officemathrenderer/)(OfficeMath) | Bu sınıfın yeni bir örneğini başlatır. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [BoundsInPoints](../../aspose.words.rendering/noderendererbase/boundsinpoints/) { get; } | Şeklin gerçek sınırlarını nokta olarak alır. |
| [OpaqueBoundsInPoints](../../aspose.words.rendering/noderendererbase/opaqueboundsinpoints/) { get; } | Şeklin opak sınırlarını nokta olarak alır. |
| [SizeInPoints](../../aspose.words.rendering/noderendererbase/sizeinpoints/) { get; } | Şeklin gerçek boyutunu nokta olarak alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetBoundsInPixels](../../aspose.words.rendering/noderendererbase/getboundsinpixels/)(float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin sınırlarını piksel cinsinden hesaplar. |
| [GetBoundsInPixels](../../aspose.words.rendering/noderendererbase/getboundsinpixels/)(float, float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin sınırlarını piksel cinsinden hesaplar. |
| [GetOpaqueBoundsInPixels](../../aspose.words.rendering/noderendererbase/getopaqueboundsinpixels/)(float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin opak sınırlarını piksel cinsinden hesaplar. |
| [GetOpaqueBoundsInPixels](../../aspose.words.rendering/noderendererbase/getopaqueboundsinpixels/)(float, float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin opak sınırlarını piksel cinsinden hesaplar. |
| [GetSizeInPixels](../../aspose.words.rendering/noderendererbase/getsizeinpixels/)(float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin boyutunu piksel cinsinden hesaplar. |
| [GetSizeInPixels](../../aspose.words.rendering/noderendererbase/getsizeinpixels/)(float, float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için şeklin boyutunu piksel cinsinden hesaplar. |
| [RenderToScale](../../aspose.words.rendering/noderendererbase/rendertoscale/)(Graphics, float, float, float) | Şekli birGraphics belirli bir ölçeğe nesne. |
| [RenderToSize](../../aspose.words.rendering/noderendererbase/rendertosize/)(Graphics, float, float, float, float) | Şekli birGraphics belirli bir boyuta nesne. |
| [Save](../../aspose.words.rendering/noderendererbase/save/)(Stream, ImageSaveOptions) | Şekli bir görüntüye dönüştürür ve bir akışa kaydeder. |
| [Save](../../aspose.words.rendering/noderendererbase/save/)(string, ImageSaveOptions) | Şekli bir görüntüye dönüştürür ve bir dosyaya kaydeder. |

### Örnekler

Şekillerin nasıl ölçüleceğini ve ölçekleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Oluşturduğumuzda OfficeMath nesnesinin oluşturacağı görüntünün boyutunu doğrulayın.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Saydam kısımlara sahip şekiller, "OpaqueBoundsInPoints" özelliklerinde farklı değerler içerebilir.
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Belirli bir DPI'ye doğrusal ölçekleme ile şekil boyutunu piksel olarak alın.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Şekil boyutunu piksel olarak alın, ancak yatay ve dikey boyutlar için farklı bir DPI ile.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// Opak sınırlar burada da değişebilir.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Ayrıca bakınız

* class [NodeRendererBase](../noderendererbase/)
* ad alanı [Aspose.Words.Rendering](../../aspose.words.rendering/)
* toplantı [Aspose.Words](../../)


