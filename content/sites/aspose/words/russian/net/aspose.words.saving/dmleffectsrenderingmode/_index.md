---
title: Enum DmlEffectsRenderingMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.DmlEffectsRenderingMode перечисление. Указывает как эффекты DrawingML визуализируются для фиксированных форматов страниц.
type: docs
weight: 4650
url: /ru/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

Указывает, как эффекты DrawingML визуализируются для фиксированных форматов страниц.

```csharp
public enum DmlEffectsRenderingMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Simplified | `0` | Упрощен рендеринг эффектов DrawingML. |
| None | `1` | Эффекты DrawingML не визуализируются. |
| Fine | `2` | Эффекты DrawingML визуализируются в точном режиме, который включает расширенную обработку. В этом режиме визуализация эффектов дает лучшие результаты, но требует более высокой производительности, чемSimplified режим. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


