---
title: PdfSaveOptions.DmlEffectsRenderingMode
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает значение определяющее способ визуализации эффектов DrawingML.
type: docs
weight: 80
url: /ru/net/aspose.words.saving/pdfsaveoptions/dmleffectsrenderingmode/
---
## PdfSaveOptions.DmlEffectsRenderingMode property

Получает или задает значение, определяющее способ визуализации эффектов DrawingML.

```csharp
public override DmlEffectsRenderingMode DmlEffectsRenderingMode { get; set; }
```

### Примечания

Значение по умолчанию:Simplified .

Это свойство используется, когда документ экспортируется в фиксированные форматы страниц.

Если[`Compliance`](../compliance/) установлен наPdfA1a или жеPdfA1b , свойство всегда возвращаетNone.

### Примеры

Показывает, как настроить качество рендеринга эффектов DrawingML в документе при его сохранении в формате PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "DmlEffectsRenderingMode" значение "DmlEffectsRenderingMode.None", чтобы отменить все эффекты DrawingML.
// Установите для свойства "DmlEffectsRenderingMode" значение "DmlEffectsRenderingMode.Simplified"
// для визуализации упрощенной версии эффектов DrawingML.
// Установите для свойства "DmlEffectsRenderingMode" значение "DmlEffectsRenderingMode.Fine", чтобы
// визуализировать эффекты DrawingML с большей точностью, а также с большей стоимостью обработки.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Смотрите также

* enum [DmlEffectsRenderingMode](../../dmleffectsrenderingmode/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


