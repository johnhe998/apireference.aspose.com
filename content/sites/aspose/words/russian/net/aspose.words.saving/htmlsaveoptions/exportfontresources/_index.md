---
title: HtmlSaveOptions.ExportFontResources
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает следует ли экспортировать ресурсы шрифта в HTML MHTML или EPUB. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 150
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportfontresources/
---
## HtmlSaveOptions.ExportFontResources property

Указывает, следует ли экспортировать ресурсы шрифта в HTML, MHTML или EPUB. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportFontResources { get; set; }
```

### Примечания

Экспорт ресурсов шрифтов обеспечивает согласованную визуализацию документов независимо от шрифтов, доступных в среде данного пользователя.

Если`ExportFontResources` установлен на`истинный` , основной документ HTML будет ссылаться на каждый шрифт через CSS 3 **@шрифт-лицо**at-rule и шрифты будут выводиться отдельными файлами. При экспорте в форматы IDPF EPUB или MHTML шрифты будут встроены в соответствующий пакет вместе с другими вспомогательными файлами.

Если[`ExportFontsAsBase64`](../exportfontsasbase64/) установлен на`истинный` , шрифты не будут сохраняться в отдельные файлы. Вместо этого они будут встроены в **@шрифт-лицо** at-правила в кодировке Base64.

**Важный!** При экспорте ресурсов шрифтов следует учитывать вопросы лицензирования шрифтов. Авторы, которые хотят использовать определенные шрифты через механизм шрифтов downloadable , должны всегда тщательно проверять, что их предполагаемое использование находится в рамках лицензии на шрифт. Многие коммерческие шрифты в настоящее время не позволяют загружать свои шрифты из Интернета в любой форме. В лицензионных соглашениях, распространяющихся на некоторые шрифты, особо отмечается, что использование через **@шрифт-лицо** rules в таблицах стилей CSS не допускается. Подмножество шрифтов также может нарушать условия лицензии.

### Примеры

Показывает, как определить пользовательскую логику для экспорта шрифтов при сохранении в HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Настройте объект SaveOptions для экспорта шрифтов в отдельные файлы.
    // Установите обратный вызов, который будет обрабатывать сохранение шрифта в пользовательском порядке.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // Обратный вызов экспортирует файлы .ttf и сохраняет их вместе с выходным документом.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Выводит информацию об экспортированных шрифтах и сохраняет их в той же локальной системной папке, что и их выходной .html.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // Мы также можем получить доступ к исходному документу отсюда.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Есть два способа сохранить экспортированный шрифт.
        // 1 - Сохраните его в локальной файловой системе:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Сохраняем в поток:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


