---
title: Enum EmfPlusDualRenderingMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.EmfPlusDualRenderingMode перечисление. Указывает как Aspose.Words должен отображать метафайлы EMF Dual.
type: docs
weight: 4720
url: /ru/net/aspose.words.saving/emfplusdualrenderingmode/
---
## EmfPlusDualRenderingMode enumeration

Указывает, как Aspose.Words должен отображать метафайлы EMF+ Dual.

```csharp
public enum EmfPlusDualRenderingMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| EmfPlusWithFallback | `0` | Aspose.Words пытается визуализировать EMF+ часть метафайла EMF+ Dual. Если некоторые записи EMF+ не поддерживаются , Aspose.Words отображает EMF как часть метафайла EMF+ Dual. |
| EmfPlus | `1` | Aspose.Words визуализирует EMF+ часть метафайла EMF+ Dual. |
| Emf | `2` | Aspose.Words визуализирует EMF как часть метафайла EMF+ Dual. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


