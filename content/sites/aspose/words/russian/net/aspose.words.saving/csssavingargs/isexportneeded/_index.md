---
title: CssSavingArgs.IsExportNeeded
second_title: Справочник по API Aspose.Words для .NET
description: CssSavingArgs свойство. Позволяет указать будет ли CSS экспортироваться в файл и внедряться в документ HTML. По умолчаниюистинный . Когда это свойствоЛОЖЬ  информация CSS не будет сохранена в файле CSS и не будет встроена в документ HTML.
type: docs
weight: 30
url: /ru/net/aspose.words.saving/csssavingargs/isexportneeded/
---
## CssSavingArgs.IsExportNeeded property

Позволяет указать, будет ли CSS экспортироваться в файл и внедряться в документ HTML. По умолчанию`истинный` . Когда это свойство`ЛОЖЬ` , информация CSS не будет сохранена в файле CSS и не будет встроена в документ HTML.

```csharp
public bool IsExportNeeded { get; set; }
```

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

* class [CssSavingArgs](../)
* пространство имен [Aspose.Words.Saving](../../csssavingargs/)
* сборка [Aspose.Words](../../../)


