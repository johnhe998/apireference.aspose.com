---
title: ThemeFonts.Latin
second_title: Aspose.Words لمراجع .NET API
description: ThemeFonts ملكية. يحدد اسم الخط للأحرف اللاتينية.
type: docs
weight: 30
url: /ar/net/aspose.words.themes/themefonts/latin/
---
## ThemeFonts.Latin property

يحدد اسم الخط للأحرف اللاتينية.

```csharp
public string Latin { get; set; }
```

### أمثلة

يوضح كيفية تعيين ألوان وخطوط مخصصة للسمات.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// يتيح لنا كائن "Theme" الوصول إلى سمة المستند ، وهي مصدر للخطوط والألوان الافتراضية.
Theme theme = doc.Theme;

// بعض الأنماط ، مثل "العنوان 1" و "العنوان الفرعي" ، ترث هذه الخطوط.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// قد تحتوي اللغات الأخرى أيضًا على خطوطها المخصصة في هذا الموضوع.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// تحتوي الخاصية "Colors" على لوحة الألوان من Microsoft Word ،
// الذي يظهر عند تغيير التظليل أو لون الخط.
// قم بتطبيق ألوان مخصصة على لوحة الألوان حتى نتمكن من الوصول إليها بسهولة في Microsoft Word
// عندما نقوم ، على سبيل المثال ، بتغيير لون الخط عبر "الصفحة الرئيسية" - >; "الخط" - >. "لون الخط"،
// أو أدخل شكلًا ، ثم قم بتعيين لون له عبر "تنسيق الشكل" - >; "أنماط الشكل".
ThemeColors colors = theme.Colors;
colors.Dark1 = Color.MidnightBlue;
colors.Light1 = Color.PaleGreen;
colors.Dark2 = Color.Indigo;
colors.Light2 = Color.Khaki;

colors.Accent1 = Color.OrangeRed;
colors.Accent2 = Color.LightSalmon;
colors.Accent3 = Color.Yellow;
colors.Accent4 = Color.Gold;
colors.Accent5 = Color.BlueViolet;
colors.Accent6 = Color.DarkViolet;

// قم بتطبيق ألوان مخصصة على الارتباطات التشعبية في حالتها التي تم النقر عليها وعدم النقر فوقها.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### أنظر أيضا

* class [ThemeFonts](../)
* مساحة الاسم [Aspose.Words.Themes](../../themefonts/)
* المجسم [Aspose.Words](../../../)


