---
title: Class MemoryFontSource
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.MemoryFontSource فصل. يمثل ملف خط TrueType الفردي المخزن في الذاكرة.
type: docs
weight: 2840
url: /ar/net/aspose.words.fonts/memoryfontsource/
---
## MemoryFontSource class

يمثل ملف خط TrueType الفردي المخزن في الذاكرة.

```csharp
public class MemoryFontSource : FontSourceBase
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [MemoryFontSource](memoryfontsource/#constructor)(byte[]) | Ctor. |
| [MemoryFontSource](memoryfontsource/#constructor_1)(byte[], int) | Ctor. |
| [MemoryFontSource](memoryfontsource/#constructor_2)(byte[], int, string) | Ctor. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/memoryfontsource/cachekey/) { get; } | مفتاح هذا المصدر في ذاكرة التخزين المؤقت . |
| [FontData](../../aspose.words.fonts/memoryfontsource/fontdata/) { get; } | بيانات الخط الثنائي . |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | إرجاع أولوية مصدر الخط. |
| override [Type](../../aspose.words.fonts/memoryfontsource/type/) { get; } | إرجاع نوع مصدر الخط. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | تم الاتصال أثناء معالجة مصدر الخط عند اكتشاف مشكلة قد تؤدي إلى فقدان الدقة في التنسيق. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | إرجاع قائمة الخطوط المتاحة عبر هذا المصدر. |

### أمثلة

يوضح كيفية استخدام مصفوفة بايت مع بيانات من ملف خط كمصدر خط.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### أنظر أيضا

* class [FontSourceBase](../fontsourcebase/)
* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


