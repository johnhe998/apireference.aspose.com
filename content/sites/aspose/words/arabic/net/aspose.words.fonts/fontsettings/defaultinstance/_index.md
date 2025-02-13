---
title: FontSettings.DefaultInstance
second_title: Aspose.Words لمراجع .NET API
description: FontSettings ملكية. إعدادات الخط الافتراضية الثابتة .
type: docs
weight: 20
url: /ar/net/aspose.words.fonts/fontsettings/defaultinstance/
---
## FontSettings.DefaultInstance property

إعدادات الخط الافتراضية الثابتة .

```csharp
public static FontSettings DefaultInstance { get; }
```

### ملاحظات

يتم استخدام هذا المثيل افتراضيًا في المستند ما لم يكن[`FontSettings`](../../../aspose.words/document/fontsettings/) محدد .

### أمثلة

يوضح كيفية تكوين مثيل إعدادات الخط الافتراضية.

```csharp
// تكوين مثيل إعدادات الخط الافتراضية لاستخدام الخط "Courier New"
// كبديل للنسخ الاحتياطي عندما نحاول استخدام خط غير معروف.
FontSettings.DefaultInstance.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Courier New";

Assert.True(FontSettings.DefaultInstance.SubstitutionSettings.DefaultFontSubstitution.Enabled);

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

// لا يحتوي هذا المستند على تكوين FontSettings. عندما نعرض المستند ،
// سيعمل مثيل FontSettings الافتراضي على حل الخط المفقود.
// Aspose.Words ستستخدم "Courier New" لعرض النص الذي يستخدم الخط غير المعروف.
Assert.Null(doc.FontSettings);

doc.Save(ArtifactsDir + "FontSettings.DefaultFontInstance.pdf");
```

يوضح كيفية استخدام واجهة IWarningCallback لمراقبة تحذيرات استبدال الخط.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Font.Name = "Times New Roman";
    builder.Writeln("Hello world!");

    FontSubstitutionWarningCollector callback = new FontSubstitutionWarningCollector();
    doc.WarningCallback = callback;

    // قم بتخزين المجموعة الحالية من مصادر الخطوط ، والتي ستكون مصدر الخط الافتراضي لكل مستند
    // التي لم نحدد مصدر خط مختلف لها.
    FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

    // لأغراض الاختبار ، سنقوم بتعيين Aspose.Words للبحث عن الخطوط فقط في مجلد غير موجود.
    FontSettings.DefaultInstance.SetFontsFolder(string.Empty, false);

    // عند تقديم المستند ، لن يكون هناك مكان للعثور على الخط "Times New Roman".
    // سيؤدي هذا إلى تحذير بشأن استبدال الخط ، والذي سيكتشفه رد الاتصال الخاص بنا.
    doc.Save(ArtifactsDir + "FontSettings.SubstitutionWarning.pdf");

    FontSettings.DefaultInstance.SetFontsSources(originalFontSources);

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Equals(
            "Font 'Times New Roman' has not been found. Using 'Fanwood' font instead. Reason: first available font."));
}

private class FontSubstitutionWarningCollector : IWarningCallback
{
    /// <summary>
    /// يتم الاتصال به في كل مرة يظهر فيها تحذير أثناء التحميل / الحفظ.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontSubstitutionWarnings.Warning(info);
    }

    public WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### أنظر أيضا

* class [FontSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsettings/)
* المجسم [Aspose.Words](../../../)


