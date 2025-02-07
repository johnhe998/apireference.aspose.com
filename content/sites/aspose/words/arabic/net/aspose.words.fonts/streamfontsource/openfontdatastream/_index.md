---
title: StreamFontSource.OpenFontDataStream
second_title: Aspose.Words لمراجع .NET API
description: StreamFontSource طريقة. يجب أن تفتح هذه الطريقة الدفق ببيانات الخط عند الطلب.
type: docs
weight: 30
url: /ar/net/aspose.words.fonts/streamfontsource/openfontdatastream/
---
## StreamFontSource.OpenFontDataStream method

يجب أن تفتح هذه الطريقة الدفق ببيانات الخط عند الطلب.

```csharp
public abstract Stream OpenFontDataStream()
```

### قيمة الإرجاع

دفق بيانات الخط.

### ملاحظات

سيتم إغلاق الدفق بعد القراءة. ليست هناك حاجة لإغلاقه بشكل صريح .

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

* class [StreamFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../streamfontsource/)
* المجسم [Aspose.Words](../../../)


