---
title: PdfSaveOptions.Compliance
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Указывает уровень соответствия стандартам PDF для выходных документов.
type: docs
weight: 30
url: /ru/net/aspose.words.saving/pdfsaveoptions/compliance/
---
## PdfSaveOptions.Compliance property

Указывает уровень соответствия стандартам PDF для выходных документов.

```csharp
public PdfCompliance Compliance { get; set; }
```

### Примечания

По умолчаниюPdf17.

### Примеры

Показывает, как установить уровень соответствия стандартам PDF для сохраненных документов PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
// Обратите внимание, что некоторые PdfSaveOptions запрещены при сохранении в один из стандартов и автоматически исправлены.
// Используйте IWarningCallback, чтобы узнать, какие параметры автоматически фиксируются.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Установите для свойства "Соответствие" значение "PdfCompliance.PdfA1b", чтобы соответствовать стандарту "PDF/A-1b",
// целью которого является сохранение внешнего вида документа, поскольку Aspose.Words преобразует его в PDF.
// Установите для свойства «Соответствие» значение «PdfCompliance.Pdf17», чтобы соответствовать стандарту «1.7».
// Установите для свойства "Соответствие" значение "PdfCompliance.PdfA1a", чтобы соответствовать стандарту "PDF/A-1a",
// что соответствует "PDF/A-1b", а также сохраняет структуру исходного документа.
// Установите для свойства «Соответствие» значение «PdfCompliance.PdfUa1», чтобы соответствовать стандарту «PDF/UA-1» (ISO 14289-1),
// который предназначен для определения представления электронных документов в формате PDF, которые обеспечивают доступ к файлу.
// Это помогает сделать документы доступными для поиска, но может значительно увеличить размер уже больших документов.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Смотрите также

* enum [PdfCompliance](../../pdfcompliance/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


