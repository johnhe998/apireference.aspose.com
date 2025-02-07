---
title: Class CssSavingArgs
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.CssSavingArgs сорт. Предоставляет данные дляCssSaving событие.
type: docs
weight: 4620
url: /ru/net/aspose.words.saving/csssavingargs/
---
## CssSavingArgs class

Предоставляет данные для[`CssSaving`](../icsssavingcallback/csssaving/) событие.

```csharp
public class CssSavingArgs
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [CssStream](../../aspose.words.saving/csssavingargs/cssstream/) { get; set; } | Позволяет указать поток, в который будет сохраняться информация CSS. |
| [Document](../../aspose.words.saving/csssavingargs/document/) { get; } | Получает объект документа, который в данный момент сохраняется. |
| [IsExportNeeded](../../aspose.words.saving/csssavingargs/isexportneeded/) { get; set; } | Позволяет указать, будет ли CSS экспортироваться в файл и внедряться в документ HTML. По умолчанию`истинный` . Когда это свойство`ЛОЖЬ` , информация CSS не будет сохранена в файле CSS и не будет встроена в документ HTML. |
| [KeepCssStreamOpen](../../aspose.words.saving/csssavingargs/keepcssstreamopen/) { get; set; } | Указывает, должен ли Aspose.Words оставить поток открытым или закрыть его после сохранения информации CSS. |

### Примечания

По умолчанию, когда Aspose.Words сохраняет документ в формате HTML, он сохраняет информацию CSS inline (как значение параметра **стиль** атрибут для каждого элемента).

`CssSavingArgs` позволяет сохранить информацию CSS в файл, предоставив собственный объект потока.

Чтобы сохранить CSS в поток, используйте[`CssStream`](./cssstream/) имущество.

Чтобы запретить сохранение CSS в файл и встраивание в HTML-документ, используйте[`IsExportNeeded`](./isexportneeded/) имущество.

### Примеры

Показывает, как работать с таблицами стилей CSS, которые создаются при преобразовании HTML.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Создаем объект "HtmlFixedSaveOptions", который мы можем передать в метод документа "Сохранить"
    // чтобы изменить способ преобразования документа в HTML.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Установите для свойства "CssStylesheetType" значение "CssStyleSheetType.External", чтобы
    // сопровождать сохраненный HTML-документ внешним файлом таблицы стилей CSS.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Ниже приведены два способа указания каталогов и имен файлов для выходных таблиц стилей CSS.
    // 1 — Используйте свойство «CssStyleSheetFileName», чтобы присвоить имя файла нашей таблице стилей:
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Используйте пользовательский обратный вызов, чтобы назвать нашу таблицу стилей:
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Устанавливает пользовательское имя файла вместе с другими параметрами для внешней таблицы стилей CSS.
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // Мы можем получить доступ ко всему исходному документу через свойство «Документ».
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


