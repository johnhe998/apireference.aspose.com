---
title: PhysicalFontInfo.FontFamilyName
second_title: Aspose.Words for .NET API Referansı
description: PhysicalFontInfo mülk. Yazı tipinin aile adı.
type: docs
weight: 20
url: /tr/net/aspose.words.fonts/physicalfontinfo/fontfamilyname/
---
## PhysicalFontInfo.FontFamilyName property

Yazı tipinin aile adı.

```csharp
public string FontFamilyName { get; }
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


