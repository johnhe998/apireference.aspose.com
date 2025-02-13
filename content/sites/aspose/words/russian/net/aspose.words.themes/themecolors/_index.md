---
title: Class ThemeColors
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Themes.ThemeColors сорт. Представляет цветовую схему темы документа которая содержит двенадцать цветов.
type: docs
weight: 6180
url: /ru/net/aspose.words.themes/themecolors/
---
## ThemeColors class

Представляет цветовую схему темы документа, которая содержит двенадцать цветов.

Объект ThemeColors содержит шесть акцентных цветов, два темных цвета, два светлых цвета и цвет для каждой гиперссылки и последующей гиперссылки.

```csharp
public class ThemeColors
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Accent1](../../aspose.words.themes/themecolors/accent1/) { get; set; } | Определяет акцент цвета 1. |
| [Accent2](../../aspose.words.themes/themecolors/accent2/) { get; set; } | Определяет акцент цвета 2. |
| [Accent3](../../aspose.words.themes/themecolors/accent3/) { get; set; } | Определяет акцент цвета 3. |
| [Accent4](../../aspose.words.themes/themecolors/accent4/) { get; set; } | Определяет акцент цвета 4. |
| [Accent5](../../aspose.words.themes/themecolors/accent5/) { get; set; } | Определяет акцент цвета 5. |
| [Accent6](../../aspose.words.themes/themecolors/accent6/) { get; set; } | Определяет акцент цвета 6. |
| [Dark1](../../aspose.words.themes/themecolors/dark1/) { get; set; } | Определяет цвет Темный 1. |
| [Dark2](../../aspose.words.themes/themecolors/dark2/) { get; set; } | Определяет цвет Темный 2. |
| [FollowedHyperlink](../../aspose.words.themes/themecolors/followedhyperlink/) { get; set; } | Определяет цвет гиперссылки, по которой щелкнули. |
| [Hyperlink](../../aspose.words.themes/themecolors/hyperlink/) { get; set; } | Определяет цвет гиперссылки. |
| [Light1](../../aspose.words.themes/themecolors/light1/) { get; set; } | Определяет цвет Light 1. |
| [Light2](../../aspose.words.themes/themecolors/light2/) { get; set; } | Определяет цвет Light 2. |

### Примеры

Показывает, как установить пользовательские цвета и шрифты для тем.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// Объект «Тема» дает нам доступ к теме документа, источнику шрифтов и цветов по умолчанию.
Theme theme = doc.Theme;

// Некоторые стили, такие как «Заголовок 1» и «Подзаголовок», наследуют эти шрифты.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// Другие языки также могут иметь собственные шрифты в этой теме.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// Свойство "Цвета" содержит цветовую палитру из Microsoft Word,
// который появляется при изменении оттенка или цвета шрифта.
// Применение пользовательских цветов к цветовой палитре, чтобы у нас был легкий доступ к ним в Microsoft Word
// когда мы, например, меняем цвет шрифта через "Home" -> "Шрифт" -> "Цвет шрифта",
// или вставьте фигуру, а затем установите для нее цвет через "Формат фигуры" -> «Стили фигур».
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

// Применяем пользовательские цвета к гиперссылкам в состоянии нажатия и отсутствия щелчка.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Themes](../../aspose.words.themes/)
* сборка [Aspose.Words](../../)


