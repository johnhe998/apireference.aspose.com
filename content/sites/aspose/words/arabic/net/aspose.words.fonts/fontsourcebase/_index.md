---
title: Class FontSourceBase
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FontSourceBase فصل. هذه فئة أساسية مجردة للفئات التي تسمح للمستخدم بتحديد مصادر خطوط مختلفة.
type: docs
weight: 2800
url: /ar/net/aspose.words.fonts/fontsourcebase/
---
## FontSourceBase class

هذه فئة أساسية مجردة للفئات التي تسمح للمستخدم بتحديد مصادر خطوط مختلفة.

```csharp
public abstract class FontSourceBase
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | إرجاع أولوية مصدر الخط. |
| abstract [Type](../../aspose.words.fonts/fontsourcebase/type/) { get; } | إرجاع نوع مصدر الخط. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | تم الاتصال أثناء معالجة مصدر الخط عند اكتشاف مشكلة قد تؤدي إلى فقدان الدقة في التنسيق. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | إرجاع قائمة الخطوط المتاحة عبر هذا المصدر. |

### أمثلة

يوضح كيفية استخدام ملف خط في نظام الملفات المحلي كمصدر للخط.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


