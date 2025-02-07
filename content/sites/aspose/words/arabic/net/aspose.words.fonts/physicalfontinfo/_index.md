---
title: Class PhysicalFontInfo
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.PhysicalFontInfo فصل. يحدد معلومات حول الخط المادي المتاح لمحرك خطوط Aspose.Words.
type: docs
weight: 2850
url: /ar/net/aspose.words.fonts/physicalfontinfo/
---
## PhysicalFontInfo class

يحدد معلومات حول الخط المادي المتاح لمحرك خطوط Aspose.Words.

```csharp
public class PhysicalFontInfo
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [FilePath](../../aspose.words.fonts/physicalfontinfo/filepath/) { get; } | المسار إلى ملف الخط إن وجد. |
| [FontFamilyName](../../aspose.words.fonts/physicalfontinfo/fontfamilyname/) { get; } | اسم عائلة الخط. |
| [FullFontName](../../aspose.words.fonts/physicalfontinfo/fullfontname/) { get; } | الاسم الكامل للخط . |
| [Version](../../aspose.words.fonts/physicalfontinfo/version/) { get; } | سلسلة إصدار الخط . |

### أمثلة

يوضح كيفية سرد الخطوط المتاحة.

```csharp
// تكوين Aspose.Words لخطوط المصدر من مجلد مخصص ، ثم طباعة كل خط متاح.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


