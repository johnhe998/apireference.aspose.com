---
title: Document.Frameset
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Bir döndürürFramesetörneğin bu belge bir çerçeve sayfasını temsil ediyorsa.
type: docs
weight: 160
url: /tr/net/aspose.words/document/frameset/
---
## Document.Frameset property

Bir döndürür`Frameset`örneğin bu belge bir çerçeve sayfasını temsil ediyorsa.

```csharp
public Frameset Frameset { get; }
```

### Notlar

Belge çerçevelenmemişse, özellik **hükümsüz** değer.

### Örnekler

Sayfadaki çerçevelere nasıl erişileceğini gösterir.

```csharp
// Belge, diğer belgelere bağlantı içeren birkaç çerçeve içeriyor.
Document doc = new Document(MyDir + "Frameset.docx");

// Varsayılan URL'yi (bir web sayfası URL'si veya yerel belge) veya çerçevenin harici bir kaynak olup olmadığını kontrol edebiliriz.
Assert.AreEqual("https://file-examples-com.github.io/uploads/2017/02/file-sample_100kB.docx",
    doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl);
Assert.True(doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile);

Assert.AreEqual("Document.docx", doc.Frameset.ChildFramesets[1].FrameDefaultUrl);
Assert.False(doc.Frameset.ChildFramesets[1].IsFrameLinkToFile);

// Çerçevelerimizden birinin özelliklerini değiştirin.
doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl =
    "https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Absolute%20position%20tab.docx";
doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile = false;
```

### Ayrıca bakınız

* class [Frameset](../../../aspose.words.framesets/frameset/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


