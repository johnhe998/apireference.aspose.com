---
title: LoadOptions.BaseUri
second_title: Aspose.Words for .NET API Referansı
description: LoadOptions mülk. Belgede bulunan göreli URIleri gerektiğinde mutlak URIlere çözümlemek için kullanılacak dizeyi alır veya ayarlar. Boş veya boş dize olabilir. Varsayılan null.
type: docs
weight: 20
url: /tr/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

Belgede bulunan göreli URI'leri gerektiğinde mutlak URI'lere çözümlemek için kullanılacak dizeyi alır veya ayarlar. Boş veya boş dize olabilir. Varsayılan null.

```csharp
public string BaseUri { get; set; }
```

### Notlar

Bu özellik, aşağıdaki durumlarda göreli URI'leri mutlak olarak çözümlemek için kullanılır:

1. Bir akıştan bir HTML belgesi yüklerken ve belge, göreli URI'leri olan görüntüler içeriyor ve BASE HTML öğesinde belirtilen bir temel URI'ye sahip değil.
2. Bir belgeyi PDF'ye ve diğer biçimlere kaydederken, ilgili URIs kullanılarak bağlanan resimleri almak için, böylece resimler çıktı belgesine kaydedilebilir.

### Örnekler

Temel URI kullanarak bir akıştan görüntüler içeren bir HTML belgesinin nasıl açılacağını gösterir.

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // Yüklerken temel klasörün URI'sini iletin
    // böylece HTML belgesinde göreli URI'leri olan herhangi bir resim bulunabilir.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // Belgenin ilk şeklinin geçerli bir resim içerdiğini doğrulayın.
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### Ayrıca bakınız

* class [LoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../loadoptions/)
* toplantı [Aspose.Words](../../../)


