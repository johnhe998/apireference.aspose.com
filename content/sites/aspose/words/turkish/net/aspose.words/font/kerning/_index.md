---
title: Font.Kerning
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Karakter aralığının başladığı yazı tipi boyutunu alır veya ayarlar.
type: docs
weight: 180
url: /tr/net/aspose.words/font/kerning/
---
## Font.Kerning property

Karakter aralığının başladığı yazı tipi boyutunu alır veya ayarlar.

```csharp
public double Kerning { get; set; }
```

### Örnekler

Karakter aralığının etkili olmaya başladığı yazı tipi boyutunun nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// Oluşturucunun yazı tipi boyutunu ve karakter aralığının etkili olacağı minimum boyutu ayarlayın.
// Yazı tipi boyutu karakter aralığı eşiğinin altına düşer, bu nedenle aşağıdaki çalıştırmada karakter aralığı olmaz.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// Karakter aralığı eşiğini, oluşturucunun mevcut yazı tipi boyutunun üzerinde olacak şekilde ayarlayın.
// Bu noktadan itibaren eklediğimiz herhangi bir metne karakter aralığı uygulanacaktır. Karakterler arasındaki boşluklar
// ayarlanacak ve normalde biraz daha estetik olarak hoş bir metin akışı sağlayacak.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


