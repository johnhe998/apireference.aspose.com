---
title: SvgSaveOptions.FitToViewPort
second_title: Справочник по API Aspose.Words для .NET
description: SvgSaveOptions свойство. Указывает должен ли выходной SVG заполнять доступную область просмотра окно браузера или контейнер. Если установлено значение true ширина и высота выходного SVG устанавливаются равными 100.
type: docs
weight: 30
url: /ru/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

Указывает, должен ли выходной SVG заполнять доступную область просмотра (окно браузера или контейнер). Если установлено значение true, ширина и высота выходного SVG устанавливаются равными 100%.

Значение по умолчанию неверно.

```csharp
public bool FitToViewPort { get; set; }
```

### Примеры

Показывает, как имитировать свойства изображений при преобразовании документа .docx в .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Настройте объект SvgSaveOptions для сохранения без границ страницы или выбираемого текста.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Смотрите также

* class [SvgSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../svgsaveoptions/)
* сборка [Aspose.Words](../../../)


