---
title: Enum ThemeColor
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Themes.ThemeColor перечисление. Определяет цвета темы для тем документа.
type: docs
weight: 6170
url: /ru/net/aspose.words.themes/themecolor/
---
## ThemeColor enumeration

Определяет цвета темы для тем документа.

```csharp
public enum ThemeColor
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `-1` | Нет цвета. |
| Dark1 | `0` | Темный основной цвет 1. |
| Light1 | `1` | Светлый основной цвет 1. |
| Dark2 | `2` | Темный основной цвет 2. |
| Light2 | `3` | Светлый основной цвет 2. |
| Accent1 | `4` | Акцентный цвет 1. |
| Accent2 | `5` | Акцентный цвет 2. |
| Accent3 | `6` | Акцентный цвет 3. |
| Accent4 | `7` | Акцентный цвет 4. |
| Accent5 | `8` | Акцентный цвет 5. |
| Accent6 | `9` | Акцентный цвет 6. |
| Hyperlink | `10` | Цвет гиперссылки. |
| FollowedHyperlink | `11` | Цвет гиперссылки перехода. |
| Text1 | `12` | Цвет текста 1. |
| Text2 | `13` | Цвет текста 2. |
| Background1 | `14` | Цвет фона 1. |
| Background2 | `15` | Цвет фона 2. |

### Примечания

Указанный цвет темы является ссылкой на один из предопределенных цветов темы, расположенных в разделе темы документа , что позволяет централизованно задавать информацию о цвете в документе.

### Примеры

Показывает, как создавать и использовать тематический стиль.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Создадим какой-нибудь стиль со свойствами шрифта темы.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

Показывает, как работать со шрифтами и цветами темы.

```csharp
Document doc = new Document();

// Определяем шрифты для языков, используемых по умолчанию.
doc.Theme.MinorFonts.Latin = "Algerian";
doc.Theme.MinorFonts.EastAsian = "Aharoni";
doc.Theme.MinorFonts.ComplexScript = "Andalus";

Font font = doc.Styles["Normal"].Font;
Console.WriteLine("Originally the Normal style theme color is: {0} and RGB color is: {1}\n", font.ThemeColor, font.Color);

// Мы можем использовать шрифт и цвет темы вместо значений по умолчанию.
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

// Есть несколько способов изменить их шрифт и цвет.
// 1 - Установив ThemeFont.None/ThemeColor.None:
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

// 2 - Установив имена шрифта/цвета, не относящиеся к теме:
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

### Смотрите также

* пространство имен [Aspose.Words.Themes](../../aspose.words.themes/)
* сборка [Aspose.Words](../../)


