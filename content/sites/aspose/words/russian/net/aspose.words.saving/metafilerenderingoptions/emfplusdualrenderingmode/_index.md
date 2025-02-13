---
title: MetafileRenderingOptions.EmfPlusDualRenderingMode
second_title: Справочник по API Aspose.Words для .NET
description: MetafileRenderingOptions свойство. Получает или задает значение определяющее способ отображения метафайлов EMF Dual.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/metafilerenderingoptions/emfplusdualrenderingmode/
---
## MetafileRenderingOptions.EmfPlusDualRenderingMode property

Получает или задает значение, определяющее способ отображения метафайлов EMF+ Dual.

```csharp
public EmfPlusDualRenderingMode EmfPlusDualRenderingMode { get; set; }
```

### Примечания

Двойные метафайлы EMF+ содержат как части EMF+, так и части EMF. MS Word и GDI+ всегда отображают часть EMF+. Aspose.Words в настоящее время не полностью поддерживает все записи EMF+, и в некоторых случаях результат рендеринга части EMF выглядит лучше, чем результат рендеринга части EMF+.

Этот параметр используется только тогда, когда метафайл визуализируется как векторная графика. Когда метафайл рендерится в растровое изображение, всегда используется часть EMF+.

Значение по умолчаниюEmfPlusWithFallback.

### Примеры

Показывает, как настроить параметры рендеринга, связанные с расширенным метафайлом Windows, при сохранении в PDF.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Установите для свойства "EmfPlusDualRenderingMode" значение "EmfPlusDualRenderingMode.Emf"
// для рендеринга только части EMF двойного метафайла EMF+.
// Установите для свойства "EmfPlusDualRenderingMode" значение "EmfPlusDualRenderingMode.EmfPlus", чтобы
// для рендеринга части EMF+ двойного метафайла EMF+.
// Установите для свойства "EmfPlusDualRenderingMode" значение "EmfPlusDualRenderingMode.EmfPlusWithFallback"
// для рендеринга части EMF+ двойного метафайла EMF+, если поддерживаются все записи EMF+.
// В противном случае Aspose.Words отобразит часть EMF.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// Установите для свойства «UseEmfEmbeddedToWmf» значение «true», чтобы визуализировать встроенные данные EMF
// для метафайлов, которые мы можем отображать как векторную графику.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### Смотрите также

* enum [EmfPlusDualRenderingMode](../../emfplusdualrenderingmode/)
* class [MetafileRenderingOptions](../)
* пространство имен [Aspose.Words.Saving](../../metafilerenderingoptions/)
* сборка [Aspose.Words](../../../)


