---
title: DocSaveOptions.SaveRoutingSlip
second_title: Aspose.Words for .NET API Referansı
description: DocSaveOptions mülk. Ne zamanyanlış  RoutingSlip verileri çıktı belgesine kaydedilmez. Varsayılan değer doğru .
type: docs
weight: 60
url: /tr/net/aspose.words.saving/docsaveoptions/saveroutingslip/
---
## DocSaveOptions.SaveRoutingSlip property

Ne zaman`yanlış` , RoutingSlip verileri çıktı belgesine kaydedilmez. Varsayılan değer **doğru** .

```csharp
public bool SaveRoutingSlip { get; set; }
```

### Örnekler

Daha eski Microsoft Word biçimleri için kaydetme seçeneklerinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

DocSaveOptions options = new DocSaveOptions(SaveFormat.Doc);

// Belgenin Microsoft Word veya Aspose.Words tarafından yüklenmesini koruyacak bir şifre belirleyin.
// Bunun belgenin içeriğini hiçbir şekilde şifrelemediğini unutmayın.
options.Password = "MyPassword";

// Belge bir yönlendirme fişi içeriyorsa, bu bayrağı true olarak ayarlayarak kaydederken koruyabiliriz.
options.SaveRoutingSlip = true;

doc.Save(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", options);

// Belgeyi yükleyebilmek için,
// DocSaveOptions nesnesinde belirttiğimiz parolayı bir LoadOptions nesnesinde uygulamamız gerekecek.
Assert.Throws<IncorrectPasswordException>(() => doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc"));

LoadOptions loadOptions = new LoadOptions("MyPassword");
doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", loadOptions);

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [DocSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../docsaveoptions/)
* toplantı [Aspose.Words](../../../)


