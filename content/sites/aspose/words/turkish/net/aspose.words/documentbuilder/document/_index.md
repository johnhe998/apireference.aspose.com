---
title: DocumentBuilder.Document
second_title: Aspose.Words for .NET API Referansı
description: DocumentBuilder mülk. Alır veya ayarlarDocument bu nesnenin eklendiği nesne.
type: docs
weight: 80
url: /tr/net/aspose.words/documentbuilder/document/
---
## DocumentBuilder.Document property

Alır veya ayarlar`Document` bu nesnenin eklendiği nesne.

```csharp
public Document Document { get; set; }
```

### Örnekler

Bir belgedeki bölümlere sayfa düzeni ayarlarının nasıl uygulanacağını ve geri alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Oluşturucunun geçerli bölümü için sayfa kurulum özelliklerini değiştirin ve metin ekleyin.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// Belge oluşturucu kullanarak yeni bir bölüme başlarsak,
// oluşturucunun mevcut sayfa kurulum özelliklerini devralır.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// "ClearFormatting" yöntemini kullanarak sayfa kurulum özelliklerini varsayılan değerlerine döndürebiliriz.
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

### Ayrıca bakınız

* class [Document](../../document/)
* class [DocumentBuilder](../)
* ad alanı [Aspose.Words](../../documentbuilder/)
* toplantı [Aspose.Words](../../../)


