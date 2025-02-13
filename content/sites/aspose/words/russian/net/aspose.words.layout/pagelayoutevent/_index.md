---
title: Enum PageLayoutEvent
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Layout.PageLayoutEvent перечисление. Код события возникшего во время построения и рендеринга модели макета страницы.
type: docs
weight: 3170
url: /ru/net/aspose.words.layout/pagelayoutevent/
---
## PageLayoutEvent enumeration

Код события, возникшего во время построения и рендеринга модели макета страницы.

Модель макета страницы строится в два этапа. Первый, «этап преобразования», когда макет страницы извлекает содержимое документа и создает граф объектов. в страницы.

В зависимости от операции, которая запустила сборку, модель макета страницы может быть преобразована в фиксированный формат страницы, а может и нет.

```csharp
public enum PageLayoutEvent
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Значение по умолчанию |
| WatchDog | `1` | Соответствует контрольной точке в коде, которая часто посещается и подходит для прерывания процесса. |
| BuildStarted | `2` | Начата сборка макета страницы. Запущено один раз. Это первое событие, которое происходит, когда[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) называется . |
| BuildFinished | `3` | Сборка макета страницы завершена. Выпущено один раз. Это последнее событие, которое происходит, когда[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) называется . |
| ConversionStarted | `4` | Начато преобразование модели документа в макет страницы. Запущено один раз. Это происходит, когда модель макета начинает извлекать содержимое документа. |
| ConversionFinished | `5` | Преобразование модели документа в макет страницы завершено. Запущено один раз. Это происходит, когда модель макета перестает извлекать содержимое документа. |
| ReflowStarted | `6` | Начата перекомпоновка макета страницы. Запущено один раз. Это происходит, когда модель макета начинает переформатировать содержимое документа. |
| ReflowFinished | `7` | Перекомпоновка макета страницы завершена. Запущено один раз. Это происходит, когда модель макета перестает перекомпоновывать содержимое документа. |
| PartReflowStarted | `8` | Началась перекомпоновка страницы. Обратите внимание, что страница может перекомпоновываться несколько раз, и эта перекомпоновка может перезапускаться до ее завершения. |
| PartReflowFinished | `9` | Перекомпоновка страницы завершена. Обратите внимание, что страница может перекомпоновываться несколько раз, и эта перекомпоновка может перезапускаться до ее завершения. |
| PartRenderingStarted | `10` | Начат рендеринг страницы. Запускается один раз на странице. |
| PartRenderingFinished | `11` | Рендеринг страницы завершен. Запускается один раз на странице. |

### Примеры

Показывает, как отслеживать изменения макета с помощью обратного вызова макета.

```csharp
[Test]
public void PageLayoutCallback()
{
    Document doc = new Document();
    doc.BuiltInDocumentProperties.Title = "My Document";

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world!");

    doc.LayoutOptions.Callback = new RenderPageLayoutCallback();
    doc.UpdatePageLayout();

    doc.Save(ArtifactsDir + "Layout.PageLayoutCallback.pdf");
}

/// <summary>
/// Уведомляет нас, когда мы сохраняем документ в фиксированном формате страницы
/// и отображает страницу, на которой мы выполняем перекомпоновку страницы, в изображение в локальной файловой системе.
/// </summary>
private class RenderPageLayoutCallback : IPageLayoutCallback
{
    public void Notify(PageLayoutCallbackArgs a)
    {
        switch (a.Event)
        {
            case PageLayoutEvent.PartReflowFinished:
                NotifyPartFinished(a);
                break;
            case PageLayoutEvent.ConversionFinished:
                NotifyConversionFinished(a);
                break;
        }
    }

    private void NotifyPartFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Part at page {a.PageIndex + 1} reflow.");
        RenderPage(a, a.PageIndex);
    }

    private void NotifyConversionFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Document \"{a.Document.BuiltInDocumentProperties.Title}\" converted to page format.");
    }

    private void RenderPage(PageLayoutCallbackArgs a, int pageIndex)
    {
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png) { PageSet = new PageSet(pageIndex) };

        using (FileStream stream =
            new FileStream(ArtifactsDir + $@"PageLayoutCallback.page-{pageIndex + 1} {++mNum}.png",
                FileMode.Create))
            a.Document.Save(stream, saveOptions);
    }

    private int mNum;
}
```

### Смотрите также

* пространство имен [Aspose.Words.Layout](../../aspose.words.layout/)
* сборка [Aspose.Words](../../)


