---
title: Enum SectionLayoutMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.SectionLayoutMode Sıralama. Belge ızgara davranışını tanımlamaya izin veren bir bölümün yerleşim modunu belirtir.
type: docs
weight: 5460
url: /tr/net/aspose.words/sectionlayoutmode/
---
## SectionLayoutMode enumeration

Belge ızgara davranışını tanımlamaya izin veren bir bölümün yerleşim modunu belirtir.

```csharp
public enum SectionLayoutMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Default | `0` | Belgedeki ilgili bölümün içeriğine hiçbir belge ızgarasının uygulanmayacağını belirtir. |
| Grid | `1` | Sayfa başına belirli bir satır ve satır başına karakter sayısını korumak için ilgili bölümün hem ek satır aralığı hem de pitch karakterinin her satıra ve karaktere eklenmesi gerektiğini belirtir. Karakterler, kılavuz çizgileriyle otomatik olarak hizalanmayacaktır. yazarak. |
| LineGrid | `2` | Sayfa başına belirtilen satır sayısını korumak için ilgili bölümün it içindeki her satıra ek satır aralığı eklenmesi gerektiğini belirtir. |
| SnapToChars | `3` | Sayfa başına belirli bir sayıda satır ve satır başına karakter sağlamak için ilgili bölümün hem ek satır aralığı hem de pitch karakterinin her satıra ve içindeki karaktere eklenmesi gerektiğini belirtir. Karakterler, yazarken kılavuz çizgileriyle otomatik olarak hizalanır. |

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

Her sayfanın sahip olabileceği satır sayısı için bir sınırın nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Adım atmayı etkinleştirin ve ardından bu bölümde sayfa başına satır sayısını ayarlamak için kullanın.
// Yeterince büyük bir yazı tipi boyutu, üst üste binen karakterleri önlemek için bazı satırları bir sonraki sayfaya itecektir.
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


