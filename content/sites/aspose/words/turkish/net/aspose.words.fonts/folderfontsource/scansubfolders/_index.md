---
title: FolderFontSource.ScanSubfolders
second_title: Aspose.Words for .NET API Referansı
description: FolderFontSource mülk. Alt klasörlerin taranıp taranmayacağını belirler.
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/folderfontsource/scansubfolders/
---
## FolderFontSource.ScanSubfolders property

Alt klasörlerin taranıp taranmayacağını belirler.

```csharp
public bool ScanSubfolders { get; }
```

### Örnekler

Yazı tipi kaynağı olarak yazı tiplerini içeren bir yerel sistem klasörünün nasıl kullanılacağını gösterir.

```csharp
// Font dosyalarını içeren bir klasörden bir font kaynağı oluşturun.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Ayrıca bakınız

* class [FolderFontSource](../)
* ad alanı [Aspose.Words.Fonts](../../folderfontsource/)
* toplantı [Aspose.Words](../../../)


