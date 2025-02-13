---
title: SaveOptions.MemoryOptimization
second_title: Справочник по API Aspose.Words для .NET
description: SaveOptions свойство. Получает или задает значение определяющее следует ли выполнять оптимизацию памяти перед сохранением документа. Значение по умолчанию для этого свойства ЛОЖЬ .
type: docs
weight: 110
url: /ru/net/aspose.words.saving/saveoptions/memoryoptimization/
---
## SaveOptions.MemoryOptimization property

Получает или задает значение, определяющее, следует ли выполнять оптимизацию памяти перед сохранением документа. Значение по умолчанию для этого свойства: **ЛОЖЬ** .

```csharp
public bool MemoryOptimization { get; set; }
```

### Примечания

Установка для этого параметра значения true может значительно снизить потребление памяти при сохранении больших документов за счет замедления времени сохранения.

### Примеры

Отображает возможность оптимизации потребления памяти при преобразовании больших документов в формат PDF.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// Установите для свойства "MemoryOptimization" значение "true", чтобы уменьшить объем памяти, занимаемой операциями сохранения больших документов.
// ценой увеличения продолжительности операции.
// Установите для свойства «MemoryOptimization» значение «false», чтобы нормально сохранить документ в формате PDF.
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### Смотрите также

* class [SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../saveoptions/)
* сборка [Aspose.Words](../../../)


