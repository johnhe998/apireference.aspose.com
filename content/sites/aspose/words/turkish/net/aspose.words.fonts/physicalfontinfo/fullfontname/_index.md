---
title: PhysicalFontInfo.FullFontName
second_title: Aspose.Words for .NET API Referansı
description: PhysicalFontInfo mülk. Yazı tipinin tam adı.
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/physicalfontinfo/fullfontname/
---
## PhysicalFontInfo.FullFontName property

Yazı tipinin tam adı.

```csharp
public string FullFontName { get; }
```

### Örnekler

Kullanılabilir yazı tiplerinin nasıl listeleneceğini gösterir.

```csharp
// Aspose.Words'ü fontları özel bir klasörden kaynaklayacak şekilde yapılandırın ve ardından mevcut her fontu yazdırın.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### Ayrıca bakınız

* class [PhysicalFontInfo](../)
* ad alanı [Aspose.Words.Fonts](../../physicalfontinfo/)
* toplantı [Aspose.Words](../../../)


