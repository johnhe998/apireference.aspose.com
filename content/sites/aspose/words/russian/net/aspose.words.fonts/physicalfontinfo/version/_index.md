---
title: PhysicalFontInfo.Version
second_title: Справочник по API Aspose.Words для .NET
description: PhysicalFontInfo свойство. Строка версии шрифта.
type: docs
weight: 40
url: /ru/net/aspose.words.fonts/physicalfontinfo/version/
---
## PhysicalFontInfo.Version property

Строка версии шрифта.

```csharp
public string Version { get; }
```

### Примеры

Показывает, как составить список доступных шрифтов.

```csharp
// Настройте Aspose.Words для получения шрифтов из пользовательской папки, а затем распечатайте каждый доступный шрифт.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### Смотрите также

* class [PhysicalFontInfo](../)
* пространство имен [Aspose.Words.Fonts](../../physicalfontinfo/)
* сборка [Aspose.Words](../../../)


