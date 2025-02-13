---
title: Enum PdfPermissions
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfPermissions перечисление. Определяет операции разрешенные пользователю для зашифрованного документа PDF.
type: docs
weight: 5230
url: /ru/net/aspose.words.saving/pdfpermissions/
---
## PdfPermissions enumeration

Определяет операции, разрешенные пользователю для зашифрованного документа PDF.

```csharp
[Flags]
public enum PdfPermissions
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| DisallowAll | `0` | Запрещает все операции с документом PDF. Это значение по умолчанию. |
| AllowAll | `FFFF` | Разрешает все операции с документом PDF. |
| ContentCopy | `10` | Копировать или иным образом извлекать текст и графику из документа с помощью операций, отличных от контролируемых пользователемContentCopyForAccessibility . |
| ContentCopyForAccessibility | `200` | Извлечь текст и графику (для обеспечения доступности для пользователей с ограниченными возможностями или для других целей). |
| ModifyContents | `8` | Изменить содержимое документа с помощью операций, отличных от тех, которые контролируются ModifyAnnotations ,FillIn , а такжеDocumentAssembly . |
| ModifyAnnotations | `20` | Добавьте или измените текстовые аннотации, заполните поля интерактивной формы и, еслиModifyContents is также задавать, создавать или изменять поля интерактивной формы (включая поля подписи). |
| FillIn | `100` | Заполните существующие поля интерактивной формы (включая поля подписи), даже еслиModifyContents ясно. |
| DocumentAssembly | `400` | Соберите документ (вставьте, поверните или удалите страницы и создайте элементы структуры документа или изображения thumbnail ), даже еслиModifyContents понятно. |
| Printing | `4` | Распечатать документ (возможно, не на самом высоком уровне качества, в зависимости от того, HighResolutionPrintingтакже установлен). |
| HighResolutionPrinting | `804` | Распечатайте документ в представление, из которого может быть сгенерирована точная цифровая копия содержимого PDF на основе алгоритма, зависящего от реализации. Когда этот флаг снят (и Printing установлен), печать должна быть ограничена низкоуровневым представлением внешнего вида, возможно ухудшенного качества. |

### Примеры

Показывает, как установить разрешения для сохраненного документа PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Начните с запрета всех разрешений.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Расширить права, чтобы разрешить редактирование аннотаций.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Включить шифрование через свойство EncryptionDetails.
saveOptions.EncryptionDetails = encryptionDetails;

// Когда мы откроем этот документ, нам нужно будет указать пароль, прежде чем получить доступ к его содержимому.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


