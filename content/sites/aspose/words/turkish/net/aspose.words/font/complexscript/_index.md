---
title: Font.ComplexScript
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Bu çalıştırmanın içeriğinin bu çalıştırma için biçimlendirme belirlenirken Unicode karakter değerlerinden bağımsız olarak karmaşık kod metni olarak ele alınıp alınmayacağını belirtir.
type: docs
weight: 80
url: /tr/net/aspose.words/font/complexscript/
---
## Font.ComplexScript property

Bu çalıştırmanın içeriğinin, bu çalıştırma için biçimlendirme belirlenirken Unicode karakter değerlerinden bağımsız olarak karmaşık kod metni olarak ele alınıp alınmayacağını belirtir.

```csharp
public bool ComplexScript { get; set; }
```

### Örnekler

Her zaman karmaşık komut dosyası olarak kabul edilen metnin nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.ComplexScript = true;

builder.Writeln("Text treated as complex script.");

doc.Save(ArtifactsDir + "Font.ComplexScript.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


