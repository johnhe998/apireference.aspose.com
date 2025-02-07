---
title: Enum PdfCustomPropertiesExport
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfCustomPropertiesExport перечисление. Указывает путьCustomDocumentProperties экспортируются в файл PDF.
type: docs
weight: 5140
url: /ru/net/aspose.words.saving/pdfcustompropertiesexport/
---
## PdfCustomPropertiesExport enumeration

Указывает путь[`CustomDocumentProperties`](../../aspose.words/document/customdocumentproperties/) экспортируются в файл PDF.

```csharp
public enum PdfCustomPropertiesExport
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Пользовательские свойства не экспортируются. |
| Standard | `1` | Пользовательские свойства экспортируются как записи в словарь /Info. |
| Metadata | `2` | Пользовательские свойства — это метаданные. |

### Примеры

Показывает, как экспортировать пользовательские свойства при преобразовании документа в PDF.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("Company", "My value");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "CustomPropertiesExport" значение "PdfCustomPropertiesExport.None", чтобы отказаться
 // настраиваемые свойства документа при сохранении документа в формате .PDF.
// Установите для свойства "CustomPropertiesExport" значение "PdfCustomPropertiesExport.Standard"
// для сохранения пользовательских свойств в выходном PDF-документе.
// Установите для свойства "CustomPropertiesExport" значение "PdfCustomPropertiesExport.Metadata"
// для сохранения пользовательских свойств в пакете XMP.
options.CustomPropertiesExport = pdfCustomPropertiesExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.CustomPropertiesExport.pdf", options);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


