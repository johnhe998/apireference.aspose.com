---
title: ViewOptions.ZoomType
second_title: Справочник по API Aspose.Words для .NET
description: ViewOptions свойство. Получает или задает значение масштабирования в зависимости от размера окна.
type: docs
weight: 60
url: /ru/net/aspose.words.settings/viewoptions/zoomtype/
---
## ViewOptions.ZoomType property

Получает или задает значение масштабирования в зависимости от размера окна.

```csharp
public ZoomType ZoomType { get; set; }
```

### Примеры

Показывает, как установить пользовательский коэффициент масштабирования, который старые версии Microsoft Word будут применять к документу при загрузке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

Показывает, как установить пользовательский тип масштабирования, который старые версии Microsoft Word будут применять к документу при загрузке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Установите для свойства "ZoomType" значение "ZoomType.PageWidth", чтобы получить Microsoft Word
// для автоматического масштабирования документа по ширине страницы.
// Установите для свойства "ZoomType" значение "ZoomType.FullPage", чтобы получить Microsoft Word
// для автоматического масштабирования документа, чтобы была видна вся первая страница.
// Установите для свойства "ZoomType" значение "ZoomType.TextFit", чтобы получить Microsoft Word
// для автоматического масштабирования документа, чтобы он соответствовал внутренним полям текста первой страницы.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Смотрите также

* enum [ZoomType](../../zoomtype/)
* class [ViewOptions](../)
* пространство имен [Aspose.Words.Settings](../../viewoptions/)
* сборка [Aspose.Words](../../../)


