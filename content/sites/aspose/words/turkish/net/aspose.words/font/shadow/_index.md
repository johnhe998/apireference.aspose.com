---
title: Font.Shadow
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Yazı tipi gölgeli olarak biçimlendirilmişse doğrudur.
type: docs
weight: 330
url: /tr/net/aspose.words/font/shadow/
---
## Font.Shadow property

Yazı tipi gölgeli olarak biçimlendirilmişse doğrudur.

```csharp
public bool Shadow { get; set; }
```

### Örnekler

Gölge ile biçimlendirilmiş bir metin dizisinin nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir ofset gölge efekti uygulamak için Gölge bayrağını ayarlayın,
// harfler sayfanın üzerinde yüzüyormuş gibi görünmesini sağlar.
builder.Font.Shadow = true;
builder.Font.Size = 36;

builder.Writeln("This text has a shadow.");

doc.Save(ArtifactsDir + "Font.Shadow.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


