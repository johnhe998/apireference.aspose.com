---
title: Document.FontSettings
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Получает или задает параметры шрифта документа.
type: docs
weight: 140
url: /ru/net/aspose.words/document/fontsettings/
---
## Document.FontSettings property

Получает или задает параметры шрифта документа.

```csharp
public FontSettings FontSettings { get; set; }
```

### Примечания

Это свойство позволяет указать настройки шрифта для каждого документа. Если установлено значение null, статический шрифт по умолчанию settings [`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) будет использован.

Значение по умолчанию равно нулю.

### Примеры

Показывает, как установить правила подстановки шрифтов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();

// Источники шрифтов по умолчанию содержат первый шрифт, который используется в документе.
Assert.AreEqual(1, fontSources.Length);
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Второй шрифт "Amethysta" недоступен.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Мы можем настроить таблицу подстановки шрифтов, которая определяет
// какие шрифты Aspose.Words будет использовать вместо недоступных шрифтов.
// Установить два шрифта подстановки для "Amethysta": "Arvo" и "Courier New".
// Если первая замена недоступна, Aspose.Words попытается использовать вторую замену и так далее.
doc.FontSettings = new FontSettings();
doc.FontSettings.SubstitutionSettings.TableSubstitution.SetSubstitutes(
    "Amethysta", new[] {"Arvo", "Courier New"});

 // «Amethysta» недоступен, а правило замены гласит, что первым шрифтом для замены является «Arvo».
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

 // "Арво" тоже нет в наличии, а "Курьер Новый" есть.
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Courier New"));

// В выходном документе будет отображаться текст, в котором используется шрифт «Amethysta» в формате «Courier New».
doc.Save(ArtifactsDir + "FontSettings.TableSubstitution.pdf");
```

### Смотрите также

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


