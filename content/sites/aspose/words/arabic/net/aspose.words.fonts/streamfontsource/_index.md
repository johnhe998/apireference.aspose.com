---
title: Class StreamFontSource
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.StreamFontSource فصل. الفئة الأساسية لمصدر خط التدفق المحدد من قبل المستخدم.
type: docs
weight: 2860
url: /ar/net/aspose.words.fonts/streamfontsource/
---
## StreamFontSource class

الفئة الأساسية لمصدر خط التدفق المحدد من قبل المستخدم.

```csharp
public abstract class StreamFontSource : FontSourceBase
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/streamfontsource/cachekey/) { get; } | مفتاح هذا المصدر في ذاكرة التخزين المؤقت . |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | إرجاع أولوية مصدر الخط. |
| [Type](../../aspose.words.fonts/streamfontsource/type/) { get; } | إرجاع نوع مصدر الخط. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | تم الاتصال أثناء معالجة مصدر الخط عند اكتشاف مشكلة قد تؤدي إلى فقدان الدقة في التنسيق. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | إرجاع قائمة الخطوط المتاحة عبر هذا المصدر. |
| abstract [OpenFontDataStream](../../aspose.words.fonts/streamfontsource/openfontdatastream/)() | يجب أن تفتح هذه الطريقة الدفق ببيانات الخط عند الطلب. |

### ملاحظات

من أجل استخدام مصدر خط الدفق ، يجب عليك إنشاء فئة مشتقة من ملف`StreamFontSource` وتقديم تنفيذ[`OpenFontDataStream`](./openfontdatastream/) طريقة.

[`OpenFontDataStream`](./openfontdatastream/)يمكن استدعاء الطريقة عدة مرات. لأول مرة سيتم استدعاؤه عندما يقوم Aspose.Words بمسح مصادر الخطوط المتوفرة للحصول على قائمة الخطوط المتاحة. لاحقًا قد يتم استدعاؤه إذا تم استخدام الخط في المستند لتحليل بيانات الخط ولتضمين بيانات الخط في بعض تنسيقات الإخراج.

`StreamFontSource` قد يكون مفيدًا لأنه يسمح بتحميل بيانات الخط فقط عندما تكون مطلوبة وليس لتخزينها في الذاكرة من أجل[`FontSettings`](../fontsettings/) حياة.

### أمثلة

يوضح كيفية تحميل الخطوط من الدفق.

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// قم بتحميل بيانات الخط عند الحاجة فقط بدلاً من تخزينها في الذاكرة
/// لكامل عمر الكائن "FontSettings".
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### أنظر أيضا

* class [FontSourceBase](../fontsourcebase/)
* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


