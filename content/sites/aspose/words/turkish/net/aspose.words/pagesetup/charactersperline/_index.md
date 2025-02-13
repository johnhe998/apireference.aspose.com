---
title: PageSetup.CharactersPerLine
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Belge ızgarasındaki satır başına karakter sayısını alır veya ayarlar.
type: docs
weight: 100
url: /tr/net/aspose.words/pagesetup/charactersperline/
---
## PageSetup.CharactersPerLine property

Belge ızgarasındaki satır başına karakter sayısını alır veya ayarlar.

```csharp
public int CharactersPerLine { get; set; }
```

### Notlar

Özelliğin minimum değeri 1'dir. Maksimum değer, Normal stilinin sayfa genişliğine ve yazı tipi boyutuna bağlıdır. Minimum karakter aralığı, yazı tipi boyutunun yüzde 90'ıdır. Örneğin, bir inç kenar boşluklu bir Letter sayfasının satırı başına maksimum karakter sayısı 43'tür.

Varsayılan olarak özelliğin, üzerinde karakter aralığının Normal stilinin yazı tipi boyutuna eşit olduğu bir değeri vardır.

### Örnekler

Her satırın sahip olabileceği karakter sayısı için nasıl a belirtileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Adım atmayı etkinleştirin ve ardından bu bölümdeki satır başına karakter sayısını ayarlamak için kullanın.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// Karakter sayısı aynı zamanda yazı tipinin boyutuna da bağlıdır.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


