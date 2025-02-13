---
title: FontSettings.SetFontsFolder
second_title: Справочник по API Aspose.Words для .NET
description: FontSettings метод. Устанавливает папку в которой Aspose.Words ищет шрифты TrueType при рендеринге документов или встраивании шрифтов. Это ярлык дляSetFontsFolders для установки только одного каталога шрифтов.
type: docs
weight: 80
url: /ru/net/aspose.words.fonts/fontsettings/setfontsfolder/
---
## FontSettings.SetFontsFolder method

Устанавливает папку, в которой Aspose.Words ищет шрифты TrueType при рендеринге документов или встраивании шрифтов. Это ярлык для[`SetFontsFolders`](../setfontsfolders/) для установки только одного каталога шрифтов.

```csharp
public void SetFontsFolder(string fontFolder, bool recursive)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fontFolder | String | Папка, содержащая шрифты TrueType. |
| recursive | Boolean | Значение true для рекурсивного сканирования указанных папок на наличие шрифтов. |

### Примеры

Показывает, как установить исходный каталог шрифта.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arvo";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Наши источники шрифтов не содержат шрифт, который мы использовали для текста в этом документе.
// Если мы используем эти настройки шрифта при рендеринге этого документа,
// Aspose.Words применит резервный шрифт к тексту, шрифт которого Aspose.Words не может найти.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// В источниках шрифтов по умолчанию отсутствуют два шрифта, которые мы используем в этом документе.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Используйте метод "SetFontsFolder", чтобы установить каталог, который будет действовать как новый источник шрифта.
// Передайте «false» в качестве «рекурсивного» аргумента, чтобы включить шрифты из всех файлов шрифтов, которые находятся в каталоге
// которые мы передаем в первом аргументе, но не включаем шрифты ни в одну из подпапок этого каталога.
// Передаем «true» в качестве «рекурсивного» аргумента, чтобы включить все файлы шрифтов в каталоге, который мы передаем
// в первом аргументе, а также все шрифты в его подкаталогах.
FontSettings.DefaultInstance.SetFontsFolder(FontsDir, recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Шрифт "Amethysta" находится в подпапке каталога шрифтов.
if (recursive)
{
    Assert.AreEqual(25, newFontSources[0].GetAvailableFonts().Count);
    Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}
else
{
    Assert.AreEqual(18, newFontSources[0].GetAvailableFonts().Count);
    Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolder.pdf");

// Восстановить исходные источники шрифтов.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Смотрите также

* class [FontSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontsettings/)
* сборка [Aspose.Words](../../../)


