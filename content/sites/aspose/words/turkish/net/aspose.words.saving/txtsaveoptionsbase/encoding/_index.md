---
title: TxtSaveOptionsBase.Encoding
second_title: Aspose.Words for .NET API Referansı
description: TxtSaveOptionsBase mülk. Metin biçimlerinde dışa aktarırken kullanılacak kodlamayı belirtir. Varsayılan değer Kodlama.UTF8 .
type: docs
weight: 10
url: /tr/net/aspose.words.saving/txtsaveoptionsbase/encoding/
---
## TxtSaveOptionsBase.Encoding property

Metin biçimlerinde dışa aktarırken kullanılacak kodlamayı belirtir. Varsayılan değer **Kodlama.UTF8** .

```csharp
public Encoding Encoding { get; set; }
```

### Örnekler

Bir .txt çıktı belgesi için kodlamanın nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ASCII karakter kümesinin dışından karakterler içeren bir metin ekleyin.
builder.Write("À È Ì Ò Ù.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "TxtSaveOptions" nesnesi oluşturun
// belgeyi düz metne kaydetme şeklimizi değiştirmek için.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// "Encoding" özelliğinin, belgemizin içeriği için uygun kodlamayı içerdiğini doğrulayın.
Assert.AreEqual(System.Text.Encoding.UTF8, txtSaveOptions.Encoding);

doc.Save(ArtifactsDir + "TxtSaveOptions.Encoding.UTF8.txt", txtSaveOptions);

string docText = System.Text.Encoding.UTF8.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.Encoding.UTF8.txt"));

Assert.AreEqual("\uFEFFÀ È Ì Ò Ù.\r\n", docText);

// Uygun olmayan bir kodlamanın kullanılması, belge içeriğinin kaybolmasına neden olabilir.
txtSaveOptions.Encoding = System.Text.Encoding.ASCII;
doc.Save(ArtifactsDir + "TxtSaveOptions.Encoding.ASCII.txt", txtSaveOptions);
docText = System.Text.Encoding.ASCII.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.Encoding.ASCII.txt"));

Assert.AreEqual("? ? ? ? ?.\r\n", docText);
```

### Ayrıca bakınız

* class [TxtSaveOptionsBase](../)
* ad alanı [Aspose.Words.Saving](../../txtsaveoptionsbase/)
* toplantı [Aspose.Words](../../../)


