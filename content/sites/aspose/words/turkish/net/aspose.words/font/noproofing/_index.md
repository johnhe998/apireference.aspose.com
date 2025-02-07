---
title: Font.NoProofing
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Biçimlendirilmiş karakterler yazım denetimi yapılmadığında doğrudur.
type: docs
weight: 280
url: /tr/net/aspose.words/font/noproofing/
---
## Font.NoProofing property

Biçimlendirilmiş karakterler yazım denetimi yapılmadığında doğrudur.

```csharp
public bool NoProofing { get; set; }
```

### Örnekler

Metnin Microsoft Word tarafından yazım denetiminin nasıl engelleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Normalde, Microsoft Word, tırtıklı kırmızı alt çizgi ile yazım hatalarını vurgular.
// Metnin bir kısmını oluşturmak için "NoProofing" bayrağının ayarını kaldırabiliriz.
// tamamen devre dışı bırakırken yazım denetleyicisini atlar.
builder.Font.NoProofing = true;

builder.Writeln("Proofing has been disabled, so these spelking errrs will not display red lines underneath.");

doc.Save(ArtifactsDir + "Font.NoProofing.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


