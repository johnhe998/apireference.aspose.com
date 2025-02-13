---
title: OutlineOptions.DefaultBookmarksOutlineLevel
second_title: Aspose.Words for .NET API Referansı
description: OutlineOptions mülk. Belge anahattında Word yer imlerinin görüntüleneceği varsayılan düzeyi belirtir.
type: docs
weight: 50
url: /tr/net/aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/
---
## OutlineOptions.DefaultBookmarksOutlineLevel property

Belge anahattında Word yer imlerinin görüntüleneceği varsayılan düzeyi belirtir.

```csharp
public int DefaultBookmarksOutlineLevel { get; set; }
```

### Notlar

Bireysel yer imleri seviyesi kullanılarak belirtilebilir[`BookmarksOutlineLevels`](../bookmarksoutlinelevels/) Emlak.

belirtin ve Word yer imleri belge anahattında görüntülenmez. 1 belirtin ve Word yer işaretleri 1. düzeyde belge anahattında görüntülenecektir; 2. seviye için 2 vb.

Varsayılan 0'dır. Geçerli aralık 0 ila 9'dur.

### Örnekler

PDF'ye dönüştürdüğümüz bir belgedeki üstbilgi/altbilgilerdeki yer imlerini işlemek için gösterir.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Çıktı PDF'sinde anahat gezinme bölmesini görüntülemek için "PageMode" özelliğini "PdfPageMode.UseOutlines" olarak ayarlayın.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Tümünü görüntülemek için "DefaultBookmarksOutlineLevel" özelliğini "1" olarak ayarlayın
// çıktı PDF'sindeki anahattın ilk seviyesindeki yer imleri.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// "HeaderFooterBookmarksExportMode" özelliğini "HeaderFooterBookmarksExportMode.None" olarak ayarlayın.
// üstbilgiler/altbilgiler içindeki yer işaretlerini dışa aktarmayın.
// "HeaderFooterBookmarksExportMode" özelliğini "HeaderFooterBookmarksExportMode.First" olarak ayarlayın.
// yalnızca ilk bölümün üstbilgi/altbilgilerindeki yer işaretlerini dışa aktarın.
// "HeaderFooterBookmarksExportMode" özelliğini "HeaderFooterBookmarksExportMode.All" olarak ayarlayın.
// tüm üstbilgilerde/altbilgilerde bulunan yer imlerini dışa aktarın.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Ayrıca bakınız

* class [OutlineOptions](../)
* ad alanı [Aspose.Words.Saving](../../outlineoptions/)
* toplantı [Aspose.Words](../../../)


