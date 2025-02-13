---
title: Class FileFormatUtil
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.FileFormatUtil сорт. Предоставляет служебные методы для работы с форматами файлов такие как определение формата файла или преобразование расширений файлов в/из перечислений форматов файлов.
type: docs
weight: 2640
url: /ru/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

Предоставляет служебные методы для работы с форматами файлов, такие как определение формата файла или преобразование расширений файлов в/из перечислений форматов файлов.

```csharp
public static class FileFormatUtil
```

## Методы

| Имя | Описание |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | Преобразует тип контента IANA в перечислимое значение формата загрузки. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | Преобразует тип контента IANA в перечислимое значение формата сохранения. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | Обнаруживает и возвращает информацию о формате документа, хранящегося в потоке. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | Обнаруживает и возвращает информацию о формате документа, хранящегося в файле на диске. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | Преобразует расширение имени файла в[`SaveFormat`](../saveformat/) значение. |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | Преобразует перечислимое значение типа изображения Aspose.Words в расширение файла. Возвращаемое расширение представляет собой строчную строку с точкой в начале. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | Преобразует перечислимое значение формата загрузки в расширение файла. Возвращаемое расширение представляет собой строчную строку с точкой в начале. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | Преобразует[`LoadFormat`](../loadformat/) значение для[`SaveFormat`](../saveformat/) значение, если возможно. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | Преобразует перечислимое значение формата сохранения в расширение файла. Возвращаемое расширение представляет собой строчную строку с точкой в начале. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | Преобразует[`SaveFormat`](../saveformat/) значение для[`LoadFormat`](../loadformat/) значение, если возможно. |

### Примеры

Показывает, как определить кодировку в html-файле.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// Свойство Encoding используется только при создании объекта FileFormatInfo для html-документа.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


