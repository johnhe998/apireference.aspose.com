---
title: Class FolderFontSource
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FolderFontSource فصل. يمثل المجلد الذي يحتوي على ملفات خط TrueType.
type: docs
weight: 2700
url: /ar/net/aspose.words.fonts/folderfontsource/
---
## FolderFontSource class

يمثل المجلد الذي يحتوي على ملفات خط TrueType.

```csharp
public class FolderFontSource : FontSourceBase
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [FolderFontSource](folderfontsource/#constructor)(string, bool) | Ctor. |
| [FolderFontSource](folderfontsource/#constructor_1)(string, bool, int) | Ctor. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [FolderPath](../../aspose.words.fonts/folderfontsource/folderpath/) { get; } | المسار إلى المجلد. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | إرجاع أولوية مصدر الخط. |
| [ScanSubfolders](../../aspose.words.fonts/folderfontsource/scansubfolders/) { get; } | تحديد ما إذا كان سيتم فحص المجلدات الفرعية أم لا. |
| override [Type](../../aspose.words.fonts/folderfontsource/type/) { get; } | إرجاع نوع مصدر الخط. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | تم الاتصال أثناء معالجة مصدر الخط عند اكتشاف مشكلة قد تؤدي إلى فقدان الدقة في التنسيق. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | إرجاع قائمة الخطوط المتاحة عبر هذا المصدر. |

### أمثلة

يوضح كيفية استخدام مجلد نظام محلي يحتوي على خطوط كمصدر للخط.

```csharp
// إنشاء مصدر خط من مجلد يحتوي على ملفات الخطوط.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### أنظر أيضا

* class [FontSourceBase](../fontsourcebase/)
* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


