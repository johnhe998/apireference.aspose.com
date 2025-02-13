---
title: FontSettings.FallbackSettings
second_title: Aspose.Words لمراجع .NET API
description: FontSettings ملكية. الإعدادات المتعلقة بآلية النسخ الاحتياطي للخط .
type: docs
weight: 30
url: /ar/net/aspose.words.fonts/fontsettings/fallbacksettings/
---
## FontSettings.FallbackSettings property

الإعدادات المتعلقة بآلية النسخ الاحتياطي للخط .

```csharp
public FontFallbackSettings FallbackSettings { get; }
```

### أمثلة

يوضح كيفية توزيع الخطوط الاحتياطية عبر نطاقات رموز أحرف Unicode.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// تكوين إعدادات الخطوط لدينا للخطوط المصدر فقط من مجلد "MyFonts".
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// سيؤدي استدعاء طريقة "BuildAutomatic" إلى إنشاء مخطط احتياطي
// يوزع الخطوط التي يمكن الوصول إليها عبر أكبر عدد ممكن من رموز أحرف Unicode.
// في حالتنا ، يمكنه فقط الوصول إلى عدد قليل من الخطوط داخل مجلد "MyFonts".
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// يمكننا أيضًا تحميل مخطط بديل مخصص من ملف مثل هذا.
// يطبق هذا النظام الخط "AllegroOpen" عبر كتل Unicode "0000-00ff" ، خط "AllegroOpen" عبر "0100-024f" ،
// والخط "M + 2m" في جميع النطاقات الأخرى التي لا تغطيها الخطوط الأخرى في المخطط.
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// قم بإنشاء منشئ مستندات وضبط خطه على خط غير موجود في أي من مصادرنا.
// ستستدعي إعدادات الخط الخاصة بنا مخطط الرجوع للأحرف التي نكتبها باستخدام الخط غير المتاح.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// استخدم المنشئ لطباعة كل حرف Unicode من 0x0021 إلى 0x052F ،
// مع الخطوط الوصفية التي تقسم كتل Unicode التي حددناها في مخططنا المخصص للرجوع للخطوط.
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### أنظر أيضا

* class [FontFallbackSettings](../../fontfallbacksettings/)
* class [FontSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsettings/)
* المجسم [Aspose.Words](../../../)


