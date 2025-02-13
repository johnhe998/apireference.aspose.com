---
title: Enum ThemeColor
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Themes.ThemeColor تعداد. يحدد ألوان النسق لنسق المستند.
type: docs
weight: 6170
url: /ar/net/aspose.words.themes/themecolor/
---
## ThemeColor enumeration

يحدد ألوان النسق لنسق المستند.

```csharp
public enum ThemeColor
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `-1` | بلا لون . |
| Dark1 | `0` | اللون الرئيسي الغامق 1. |
| Light1 | `1` | اللون الرئيسي الفاتح 1. |
| Dark2 | `2` | اللون الرئيسي الداكن 2. |
| Light2 | `3` | اللون الرئيسي الفاتح 2. |
| Accent1 | `4` | لون التمييز 1. |
| Accent2 | `5` | لون التمييز 2. |
| Accent3 | `6` | لون التمييز 3. |
| Accent4 | `7` | لون التمييز 4. |
| Accent5 | `8` | لون التمييز 5. |
| Accent6 | `9` | لون التمييز 6. |
| Hyperlink | `10` | لون الارتباط التشعبي . |
| FollowedHyperlink | `11` | لون الارتباط التشعبي المتبع. |
| Text1 | `12` | لون النص 1. |
| Text2 | `13` | لون النص 2. |
| Background1 | `14` | لون الخلفية 1. |
| Background2 | `15` | لون الخلفية 2. |

### ملاحظات

لون النسق المحدد هو مرجع إلى أحد ألوان النسق المحددة مسبقًا ، والموجودة في جزء سمة المستند ، والذي يسمح بتعيين معلومات اللون مركزيًا في المستند.

### أمثلة

يوضح كيفية إنشاء واستخدام نمط ذي موضوع.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// إنشاء نمط بخصائص خط النسق.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

يوضح كيفية العمل مع خطوط وألوان النسق.

```csharp
Document doc = new Document();

// تحديد الخطوط للغات التي تستخدم بشكل افتراضي.
doc.Theme.MinorFonts.Latin = "Algerian";
doc.Theme.MinorFonts.EastAsian = "Aharoni";
doc.Theme.MinorFonts.ComplexScript = "Andalus";

Font font = doc.Styles["Normal"].Font;
Console.WriteLine("Originally the Normal style theme color is: {0} and RGB color is: {1}\n", font.ThemeColor, font.Color);

// يمكننا استخدام خط ولون المظهر بدلاً من القيم الافتراضية.
font.ThemeFont = ThemeFont.Minor;
font.ThemeColor = ThemeColor.Accent2;

Assert.AreEqual(ThemeFont.Minor, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.Accent2, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// هناك عدة طرق لإعادة تعيين الخط واللون.
// 1 - عن طريق تعيين ThemeFont.None / ThemeColor.None:
font.ThemeFont = ThemeFont.None;
font.ThemeColor = ThemeColor.None;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// 2 - عن طريق تعيين أسماء خطوط / ألوان غير متعلقة بالموضوع:
font.Name = "Arial";
font.Color = Color.Blue;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Arial", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Arial", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Arial", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Arial", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Arial", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Blue.ToArgb(), font.Color.ToArgb());
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Themes](../../aspose.words.themes/)
* المجسم [Aspose.Words](../../)


