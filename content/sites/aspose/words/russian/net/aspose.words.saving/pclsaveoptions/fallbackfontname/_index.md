---
title: PclSaveOptions.FallbackFontName
second_title: Справочник по API Aspose.Words для .NET
description: PclSaveOptions свойство. Имя шрифта который будет использоваться  если ожидаемый шрифт не найден в коллекциях принтеров и встроенных шрифтов.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

Имя шрифта, который будет использоваться , если ожидаемый шрифт не найден в коллекциях принтеров и встроенных шрифтов.

```csharp
public string FallbackFontName { get; set; }
```

### Примечания

Если резервный вариант не найден, генерируется предупреждение и используется шрифт "Arial".

### Примеры

Показывает, как объявить шрифт, который принтер будет применять к печатному тексту в качестве замены, если исходный шрифт будет недоступен.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// Этот документ предписывает принтеру применить «Times New Roman» к тексту с отсутствующим шрифтом.
// Если «Times New Roman» также будет недоступен, принтер по умолчанию будет использовать шрифт «Arial».
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### Смотрите также

* class [PclSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pclsaveoptions/)
* сборка [Aspose.Words](../../../)


