---
title: ParagraphFormat.WidowControl
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Paragraftaki ilk ve son satırlar paragrafın geri kalanıyla aynı sayfada kalacaksa doğrudur.
type: docs
weight: 390
url: /tr/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Paragraftaki ilk ve son satırlar paragrafın geri kalanıyla aynı sayfada kalacaksa doğrudur.

```csharp
public bool WidowControl { get; set; }
```

### Örnekler

Bir paragraf için dul/yetim denetiminin nasıl etkinleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir sayfaya sığmayan metni yazdığımızda bir satır sonraki sayfaya taşabilir.
// Bir sonraki sayfada biten tek satıra "Yetim" denir,
// ve yetimin ayrıldığı önceki satıra "Dul" denir.
// Yazı tipi boyutu, boşluk veya sayfa kenar boşlukları ile metni yeniden düzenleyerek yetimleri ve dulları düzeltebiliriz.
// Belgemizin boyutlarını korumak istiyorsak bu bayrağı "true" olarak ayarlayabiliriz.
 // dulları kendi yetimleriyle aynı sayfaya itmek için.
// Bu bayrağı "yanlış" olarak bırakın, metinde dul/yetim çiftleri bırakacaktır.
// Her paragrafta bu ayar Microsoft Word'de Ana Sayfa -> Paragraf -> Paragraf Ayarları
// ("Paragraf" sekmesinin sağ alt köşesindeki düğme) -> "Dul/Yetim kontrolü".
builder.ParagraphFormat.WidowControl = widowControl; 

// Yetim ve dul oluşturan metin ekleyin.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Ayrıca bakınız

* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


