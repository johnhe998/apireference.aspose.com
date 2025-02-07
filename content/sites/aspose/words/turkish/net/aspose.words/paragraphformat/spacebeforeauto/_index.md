---
title: ParagraphFormat.SpaceBeforeAuto
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Paragraftan önceki boşluk miktarı otomatik olarak ayarlanırsa doğrudur.
type: docs
weight: 320
url: /tr/net/aspose.words/paragraphformat/spacebeforeauto/
---
## ParagraphFormat.SpaceBeforeAuto property

Paragraftan önceki boşluk miktarı otomatik olarak ayarlanırsa doğrudur.

```csharp
public bool SpaceBeforeAuto { get; set; }
```

### Notlar

true olarak ayarlandığında, etkisini geçersiz kılar[`SpaceBefore`](../spacebefore/).

Paragraf Öncesi Boşluk ve Sonra Boşluğu Otomatik olarak ayarladığınızda, Microsoft Word, aşağıdaki kurallara göre paragraflar arasına otomatik olarak 14 nokta aralığı ekler:

* Normalde, tüm paragraflardan sonra boşluk eklenir.
* Madde işaretli veya numaralı bir listede, yalnızca listedeki son öğeden sonra boşluk eklenir. Liste öğeleri arasına boşluk eklenmez.
* İç içe madde işaretli veya numaralı bir listede boşluk eklenmez.
* Boşluk normalde bir tablodan sonra eklenir.
* Tablo hücresindeki son blok ise, tablodan sonra boşluk eklenmez.
* Tablo hücresinde son paragraftan sonra boşluk eklenmez.

### Örnekler

Otomatik paragraf aralığının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bu oluşturucunun oluşturacağı paragraflardan önce ve sonra büyük miktarda boşluk uygulayın.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Otomatik boşluk uygulamak için bu bayrakları "true" olarak ayarlayın,
// yukarıda belirlediğimiz özelliklerdeki boşlukları etkin bir şekilde yok sayıyoruz.
// Bunları "false" olarak bırakın, özel paragraf aralığımızı uygular.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// Altlarında ve üstlerinde boşluk olacak şekilde iki paragraf ekleyin ve belgeyi kaydedin.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

### Ayrıca bakınız

* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


