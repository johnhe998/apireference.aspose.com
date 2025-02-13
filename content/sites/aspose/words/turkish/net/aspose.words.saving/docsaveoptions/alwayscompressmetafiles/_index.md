---
title: DocSaveOptions.AlwaysCompressMetafiles
second_title: Aspose.Words for .NET API Referansı
description: DocSaveOptions mülk. Ne zamanyanlış  küçük meta dosyaları performans nedeniyle sıkıştırılmaz. Varsayılan değer doğru  boyutundan bağımsız olarak tüm meta dosyaları sıkıştırılır.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/docsaveoptions/alwayscompressmetafiles/
---
## DocSaveOptions.AlwaysCompressMetafiles property

Ne zaman`yanlış` , küçük meta dosyaları performans nedeniyle sıkıştırılmaz. Varsayılan değer **doğru** , boyutundan bağımsız olarak tüm meta dosyaları sıkıştırılır.

```csharp
public bool AlwaysCompressMetafiles { get; set; }
```

### Örnekler

Kaydederken bir belgedeki meta dosya sıkıştırmasının nasıl değiştirileceğini gösterir.

```csharp
// Microsoft Denklem 3.0 formülü içeren bir belge açın.
Document doc = new Document(MyDir + "Microsoft equation object.docx");

// Bir belgeyi kaydettiğimizde, performans nedenleriyle daha küçük meta dosyaları sıkıştırılmaz.
// Kaydederken her meta dosyasını sıkıştırmak için SaveOptions nesnesinde bir bayrak ayarlayabiliriz.
// LibreOffice gibi bazı editörler sıkıştırılmamış meta dosyaları okuyamaz.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.AlwaysCompressMetafiles = compressAllMetafiles;

doc.Save(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx", saveOptions);

if (compressAllMetafiles)
    Assert.That(10000, Is.LessThan(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
else
    Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
```

### Ayrıca bakınız

* class [DocSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../docsaveoptions/)
* toplantı [Aspose.Words](../../../)


