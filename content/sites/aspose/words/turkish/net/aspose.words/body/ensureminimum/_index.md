---
title: Body.EnsureMinimum
second_title: Aspose.Words for .NET API Referansı
description: Body yöntem. Son alt öğe bir paragraf değilse boş bir paragraf oluşturur ve ekler.
type: docs
weight: 50
url: /tr/net/aspose.words/body/ensureminimum/
---
## Body.EnsureMinimum method

Son alt öğe bir paragraf değilse, boş bir paragraf oluşturur ve ekler.

```csharp
public void EnsureMinimum()
```

### Örnekler

Belgedeki tüm bölümlerdeki ana metni siler ve bölümlerin kendilerini terk eder.

```csharp
Document doc = new Document();

// Boş bir belge bir bölüm, bir gövde ve bir paragraf içerir.
// Tüm bu düğümleri kaldırmak için "RemoveAllChildren" yöntemini çağırın,
// ve alt öğesi olmayan bir belge düğümüyle bitirin.
doc.RemoveAllChildren();

// Bu belgede artık içerik ekleyebileceğimiz bileşik alt düğüm yok.
// Düzenlemek istiyorsak, düğüm koleksiyonunu yeniden doldurmamız gerekecek.
// Önce yeni bir bölüm oluşturun ve ardından onu kök belge düğümüne alt öğe olarak ekleyin.
Section section = new Section(doc);
doc.AppendChild(section);

// Bir bölümün tüm içeriğini içerecek ve görüntüleyecek bir gövdeye ihtiyacı var
// bölümün üstbilgisi ve altbilgisi arasındaki sayfada.
Body body = new Body(doc);
section.AppendChild(body);

// Bu gövdenin çocuğu yok, bu yüzden henüz ona çalıştırma ekleyemiyoruz.
Assert.AreEqual(0, doc.FirstSection.Body.GetChildNodes(NodeType.Any, true).Count);

// Bu gövdenin en az bir boş paragraf içerdiğinden emin olmak için "EnsureMinimum" öğesini çağırın. 
body.EnsureMinimum();

// Şimdi, gövdeye çalıştırmalar ekleyebilir ve bunları görüntülemek için belgeyi alabiliriz.
body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [Body](../)
* ad alanı [Aspose.Words](../../body/)
* toplantı [Aspose.Words](../../../)


