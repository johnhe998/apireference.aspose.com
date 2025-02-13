---
title: FontSubstitutionSettings.DefaultFontSubstitution
second_title: Aspose.Words لمراجع .NET API
description: FontSubstitutionSettings ملكية. الإعدادات المتعلقة بقاعدة استبدال الخط الافتراضية.
type: docs
weight: 10
url: /ar/net/aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/
---
## FontSubstitutionSettings.DefaultFontSubstitution property

الإعدادات المتعلقة بقاعدة استبدال الخط الافتراضية.

```csharp
public DefaultFontSubstitutionRule DefaultFontSubstitution { get; }
```

### أمثلة

يوضح كيفية تعيين قاعدة استبدال الخط الافتراضي.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// احصل على قاعدة الاستبدال الافتراضية داخل FontSettings.
// ستستبدل هذه القاعدة جميع الخطوط المفقودة بـ "Times New Roman".
DefaultFontSubstitutionRule defaultFontSubstitutionRule =
    fontSettings.SubstitutionSettings.DefaultFontSubstitution;
Assert.True(defaultFontSubstitutionRule.Enabled);
Assert.AreEqual("Times New Roman", defaultFontSubstitutionRule.DefaultFontName);

// قم بتعيين بديل الخط الافتراضي على "Courier New".
defaultFontSubstitutionRule.DefaultFontName = "Courier New";

// باستخدام مُنشئ المستندات ، أضف بعض النص بخط لسنا مضطرين لرؤية الاستبدال ،
// ثم اعرض النتيجة في ملف PDF.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Missing Font";
builder.Writeln("Line written in a missing font, which will be substituted with Courier New.");

doc.Save(ArtifactsDir + "FontSettings.DefaultFontSubstitutionRule.pdf");
```

### أنظر أيضا

* class [DefaultFontSubstitutionRule](../../defaultfontsubstitutionrule/)
* class [FontSubstitutionSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsubstitutionsettings/)
* المجسم [Aspose.Words](../../../)


