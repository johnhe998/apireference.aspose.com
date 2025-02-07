---
title: SaveOutputParameters.ContentType
second_title: Aspose.Words for .NET API Referansı
description: SaveOutputParameters mülk. Kaydedilen belgenin türünü tanımlayan İçerik Türü dizesini İnternet Medya Türü döndürür.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/saveoutputparameters/contenttype/
---
## SaveOutputParameters.ContentType property

Kaydedilen belgenin türünü tanımlayan İçerik Türü dizesini (İnternet Medya Türü) döndürür.

```csharp
public string ContentType { get; }
```

### Örnekler

Bir belgenin kaydetme işleminin çıktı parametrelerine nasıl erişileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Bir belgeyi kaydettikten sonra, yeni oluşturulan çıktı belgesinin İnternet Medya Türüne (MIME türü) erişebiliriz.
SaveOutputParameters parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.doc");

Assert.AreEqual("application/msword", parameters.ContentType);

// Bu özellik kaydetme biçimine göre değişir.
parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.pdf");

Assert.AreEqual("application/pdf", parameters.ContentType);
```

### Ayrıca bakınız

* class [SaveOutputParameters](../)
* ad alanı [Aspose.Words.Saving](../../saveoutputparameters/)
* toplantı [Aspose.Words](../../../)


