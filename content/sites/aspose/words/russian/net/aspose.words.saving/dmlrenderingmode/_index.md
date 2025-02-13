---
title: Enum DmlRenderingMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.DmlRenderingMode перечисление. Указывает как фигуры DrawingML визуализируются для фиксированных форматов страниц.
type: docs
weight: 4660
url: /ru/net/aspose.words.saving/dmlrenderingmode/
---
## DmlRenderingMode enumeration

Указывает, как фигуры DrawingML визуализируются для фиксированных форматов страниц.

```csharp
public enum DmlRenderingMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Fallback | `0` | Если для DrawingML доступна резервная форма, Aspose.Words отображает резервную форму вместо DrawingML. |
| DrawingML | `1` | Aspose.Words игнорирует резервную форму DrawingML и отображает сам DrawingML. Это режим по умолчанию. |

### Примеры

Показывает, как визуализировать резервные фигуры при сохранении в PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "DmlRenderingMode" значение "DmlRenderingMode.Fallback"
// для замены форм DML их резервными формами.
// Установите для свойства "DmlRenderingMode" значение "DmlRenderingMode.DrawingML"
// для рендеринга самих форм DML.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


