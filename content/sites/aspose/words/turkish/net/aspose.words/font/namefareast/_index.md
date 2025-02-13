---
title: Font.NameFarEast
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Doğu Asya yazı tipi adını döndürür veya ayarlar.
type: docs
weight: 260
url: /tr/net/aspose.words/font/namefareast/
---
## Font.NameFarEast property

Doğu Asya yazı tipi adını döndürür veya ayarlar.

```csharp
public string NameFarEast { get; set; }
```

### Örnekler

Uzak Doğu dilinde metnin nasıl ekleneceğini ve biçimlendirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belge oluşturucunun eklediği herhangi bir metne uygulayacağı yazı tipi ayarlarını belirtin.
builder.Font.Name = "Courier New";
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Yazı tipimiz ve yerel ayarımız için "FarEast" eşdeğerlerini adlandırın.
// Oluşturucu bu Yazı Tipi yapılandırmasıyla Asya karakterlerini eklerse, aşağıdakileri içeren her çalıştırma
// bu karakterler, onları varsayılan yerine "UzakEast" yazı tipi/yerel ayarı kullanarak görüntüler.
// Bu, bir batı yazı tipinin Asya karakterleri için ideal temsilleri olmadığında faydalı olabilir.
builder.Font.NameFarEast = "SimSun";
builder.Font.LocaleIdFarEast = new CultureInfo("zh-CN", false).LCID;

// Bu metin varsayılan yazı tipinde/yerel ayarda görüntülenecektir.
builder.Writeln("Hello world!");

// Bunlar Asya karakterleri olduğundan, bu çalıştırma "Uzakdoğu" yazı tipi/yerel eşdeğerlerimizi uygulayacaktır.
builder.Writeln("你好世界");

doc.Save(ArtifactsDir + "Font.FarEast.docx");
```

### Ayrıca bakınız

* property [Name](../name/)
* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


