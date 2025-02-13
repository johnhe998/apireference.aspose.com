---
title: Сжатие изображений в документе PDF
linktitle: Сжатие изображений в документе PDF
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по сжатию изображений в PDF-документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/image-compression/
---

В этой статье представлено пошаговое руководство по использованию функции сжатия изображений в документе PDF с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как сжимать изображения в документе и создавать PDF-файл с правильным сжатием изображений.

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

## Шаг 3. Настройте параметры сохранения в формате PDF со сжатием изображений.

 Для сжатия изображений при конвертации в PDF нам нужно настроить`PdfSaveOptions` объект. При необходимости мы можем установить тип сжатия изображения, качество JPEG и другие параметры соответствия PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Шаг 4. Сохраните документ в формате PDF со сжатием изображения.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Шаг 5. Настройте параметры для сохранения в формате PDF/A-2u со сжатием изображения.

Если вы хотите создать PDF-файл, совместимый с PDF/A-2u, со сжатием изображения, вы можете настроить дополнительные параметры сохранения.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Используйте сжатие JPEG с качеством 50%, чтобы уменьшить размер файла.
};
```

## Шаг 6. Сохраните документ в формате PDF/A-2u со сжатием изображения.

Сохраните документ в формате PDF/A-2u, используя настроенные ранее дополнительные параметры сохранения.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Вот и все ! Вы успешно сжали изображения в документе и создали PDF-файл с надлежащим сжатием изображений с помощью Aspose.Words для .NET.

### Пример исходного кода для сжатия изображений с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Используйте сжатие JPEG с качеством 50%, чтобы уменьшить размер файла.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Заключение

В этом руководстве мы объяснили, как сжимать изображения в документе PDF с помощью Aspose.Words для .NET. Следуя описанным шагам, вы можете легко уменьшить размер изображений в документе PDF и создать PDF-файл с надлежащим сжатием изображения. Используйте функции сжатия изображений Aspose.Words для .NET, чтобы оптимизировать размер ваших PDF-документов при сохранении качества изображения.

### Часто задаваемые вопросы

#### В: Что такое сжатие изображения в документе PDF?
О: Сжатие изображений в документе PDF предназначено для уменьшения размера изображений, включенных в документ PDF, для уменьшения общего размера файла PDF. Это уменьшает необходимое пространство для хранения и повышает производительность при загрузке и просмотре PDF.

#### В: Как сжать изображения в документе PDF с помощью Aspose.Words for .NET?
О: Чтобы сжать изображения в документе PDF с помощью Aspose.Words for .NET, выполните следующие действия:

 Создайте экземпляр`Document` класс, указывающий путь к документу Word.

 Создайте экземпляр`PdfSaveOptions`класс и установить`ImageCompression` собственность на`PdfImageCompression.Jpeg` использовать сжатие JPEG.

Вы также можете установить другие параметры сжатия изображения, такие как качество JPEG, в соответствии с вашими потребностями.

 Использовать`Save` метод`Document`class, чтобы сохранить документ в формате PDF, указав параметры сохранения.

#### В: В чем разница между стандартным сжатием изображений и сжатием изображений PDF/A-2u?
О: Стандартное сжатие изображений уменьшает размер изображений в документе PDF при сохранении полей формы. Это уменьшает общий размер файла PDF без ущерба для функциональности полей формы.

Сжатие изображения с помощью PDF/A-2u — это дополнительная опция, позволяющая создавать файл PDF, соответствующий стандарту PDF/A-2u, с применением сжатия изображения. PDF/A-2u — это стандарт ISO для архивных PDF-документов, гарантирующий долговременную сохранность документов.
