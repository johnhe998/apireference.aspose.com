---
title: PageSetup.Bidi
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Bu bölümün iki yönlü karmaşık komut dosyaları metin içerdiğini belirtir.
type: docs
weight: 10
url: /tr/net/aspose.words/pagesetup/bidi/
---
## PageSetup.Bidi property

Bu bölümün iki yönlü (karmaşık komut dosyaları) metin içerdiğini belirtir.

```csharp
public bool Bidi { get; set; }
```

### Notlar

Doğru olduğunda, bu bölümdeki sütunlar sağdan sola doğru düzenlenir.

### Örnekler

Bir bölümdeki metin sütunlarının sırasının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TextColumns.SetCount(3);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 2.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 3.");

// Sayfanın sağ tarafından başlayarak sütunları düzenlemek için "Bidi" özelliğini "true" olarak ayarlayın.
// Sütunların sırası, sağdan sola metnin yönü ile eşleşecektir.
// Sayfanın sol tarafından başlayarak sütunları düzenlemek için "Bidi" özelliğini "false" olarak ayarlayın.
// Sütunların sırası, soldan sağa metnin yönü ile eşleşecektir.
pageSetup.Bidi = reverseColumns;

doc.Save(ArtifactsDir + "PageSetup.Bidi.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


