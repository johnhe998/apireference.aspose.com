---
title: Обновить последнее напечатанное свойство
linktitle: Обновить последнее напечатанное свойство
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по обновлению свойства «Последняя печать» при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

В этой статье представлено пошаговое руководство по использованию функции обновления свойства «Последняя печать» с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как настроить параметр для обновления свойства «Последняя печать» при преобразовании в PDF.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «Rendering.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Настройте параметры «Сохранить как PDF» с обновленным свойством «Последняя печать»

 Чтобы включить обновление свойства «Последняя печать» при преобразовании в PDF, нам нужно настроить`PdfSaveOptions` объект и установить`UpdateLastPrintedProperty` собственность на`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Шаг 4. Сохраните документ в формате PDF с обновлением свойства «Последняя печать».

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Вот и все ! Вы успешно включили обновление свойства «Последняя печать» при преобразовании документа в PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для обновления свойства «Последнее напечатанное» с помощью Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
