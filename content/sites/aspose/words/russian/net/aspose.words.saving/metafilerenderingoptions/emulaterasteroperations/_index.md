---
title: MetafileRenderingOptions.EmulateRasterOperations
second_title: Справочник по API Aspose.Words для .NET
description: MetafileRenderingOptions свойство. Получает или задает значение определяющее следует ли эмулировать растровые операции.
type: docs
weight: 30
url: /ru/net/aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/
---
## MetafileRenderingOptions.EmulateRasterOperations property

Получает или задает значение, определяющее, следует ли эмулировать растровые операции.

```csharp
public bool EmulateRasterOperations { get; set; }
```

### Примечания

В метафайлах можно использовать определенные растровые операции. Их нельзя визуализировать непосредственно в векторную графику. Эмуляция растровых операций требует частичной растеризации результирующей векторной графики, что может повлиять на производительность рендеринга метафайлов .

Когда это значение установлено на`истинный`, Aspose.Words эмулирует растровые операции. Полученный результат может быть частично растеризован, и производительность может снизиться.

Когда это значение установлено на`ЛОЖЬ`, Aspose.Words не эмулирует растровые операции. Когда Aspose.Words встречает растровую операцию в метафайле, он переходит к рендерингу метафайла в растровое изображение с помощью операционной системы .

Этот параметр используется только тогда, когда метафайл визуализируется как векторная графика.

Значение по умолчанию`истинный`.

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

* class [MetafileRenderingOptions](../)
* пространство имен [Aspose.Words.Saving](../../metafilerenderingoptions/)
* сборка [Aspose.Words](../../../)


