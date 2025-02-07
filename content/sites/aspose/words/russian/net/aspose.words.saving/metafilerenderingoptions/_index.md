---
title: Class MetafileRenderingOptions
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.MetafileRenderingOptions сорт. Позволяет указать дополнительные параметры рендеринга метафайла.
type: docs
weight: 5020
url: /ru/net/aspose.words.saving/metafilerenderingoptions/
---
## MetafileRenderingOptions class

Позволяет указать дополнительные параметры рендеринга метафайла.

```csharp
public class MetafileRenderingOptions
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [MetafileRenderingOptions](metafilerenderingoptions/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [EmfPlusDualRenderingMode](../../aspose.words.saving/metafilerenderingoptions/emfplusdualrenderingmode/) { get; set; } | Получает или задает значение, определяющее способ отображения метафайлов EMF+ Dual. |
| [EmulateRasterOperations](../../aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/) { get; set; } | Получает или задает значение, определяющее, следует ли эмулировать растровые операции. |
| [RenderingMode](../../aspose.words.saving/metafilerenderingoptions/renderingmode/) { get; set; } | Получает или задает значение, определяющее способ визуализации изображений метафайлов. |
| [ScaleWmfFontsToMetafileSize](../../aspose.words.saving/metafilerenderingoptions/scalewmffontstometafilesize/) { get; set; } | Получает или задает значение, определяющее, следует ли масштабировать шрифты в метафайле WMF в соответствии с размером метафайла на странице. |
| [UseEmfEmbeddedToWmf](../../aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/) { get; set; } | Получает или задает значение, определяющее способ отображения метафайлов WMF со встроенными метафайлами EMF. |

### Примеры

В шоу добавлен резервный вариант рендеринга растровых изображений и изменен тип предупреждений о неподдерживаемых записях метафайлов.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // Установите для свойства "EmulateRasterOperations" значение "false", чтобы вернуться к растровому изображению, когда
    // он встречает метафайл, для которого потребуются растровые операции для отображения в выходном PDF-файле.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // Установите для свойства «RenderingMode» значение «VectorWithFallback», чтобы попытаться отобразить каждый метафайл с использованием векторной графики.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
    // для изменения того, как этот метод преобразует документ в .PDF и применяет конфигурацию
    // в нашем объекте MetafileRenderingOptions для операции сохранения.
    PdfSaveOptions saveOptions = new PdfSaveOptions();
    saveOptions.MetafileRenderingOptions = metafileRenderingOptions;

    HandleDocumentWarnings callback = new HandleDocumentWarnings();
    doc.WarningCallback = callback;

    doc.Save(ArtifactsDir + "PdfSaveOptions.HandleBinaryRasterWarnings.pdf", saveOptions);

    Assert.AreEqual(1, callback.Warnings.Count);
    Assert.AreEqual("'R2_XORPEN' binary raster operation is partly supported.",
        callback.Warnings[0].Description);
}

/// <summary>
/// Выводит и собирает предупреждения о потере форматирования, возникающие при сохранении документа.
/// </summary>
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.MinorFormattingLoss)
        {
            Console.WriteLine("Unsupported operation: " + info.Description);
            Warnings.Warning(info);
        }
    }

    public WarningInfoCollection Warnings = new WarningInfoCollection();
}
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


