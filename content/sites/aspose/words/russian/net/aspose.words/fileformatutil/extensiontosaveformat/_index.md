---
title: FileFormatUtil.ExtensionToSaveFormat
second_title: Справочник по API Aspose.Words для .NET
description: FileFormatUtil метод. Преобразует расширение имени файла вSaveFormat значение.
type: docs
weight: 40
url: /ru/net/aspose.words/fileformatutil/extensiontosaveformat/
---
## FileFormatUtil.ExtensionToSaveFormat method

Преобразует расширение имени файла в[`SaveFormat`](../../saveformat/) значение.

```csharp
public static SaveFormat ExtensionToSaveFormat(string extension)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| extension | String | Расширение файла. Может быть с ведущей точкой или без нее. Без учета регистра. |

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentNullException | Выдает, если параметр имеет значение null. |

### Примечания

Если расширение не может быть распознано, возвращаетсяUnknown.

### Примеры

Показывает, как использовать методы FileFormatUtil для определения формата документа.

```csharp
// Загрузить документ из файла, в котором отсутствует расширение файла, а затем определить его формат файла.
using (FileStream docStream = File.OpenRead(MyDir + "Word document with missing file extension"))
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(docStream);
    LoadFormat loadFormat = info.LoadFormat;

    Assert.AreEqual(LoadFormat.Doc, loadFormat);

    // Ниже приведены два метода преобразования LoadFormat в соответствующий ему SaveFormat.
    // 1 — Получить строку расширения файла для LoadFormat, затем получить соответствующий SaveFormat из этой строки:
    string fileExtension = FileFormatUtil.LoadFormatToExtension(loadFormat);
    SaveFormat saveFormat = FileFormatUtil.ExtensionToSaveFormat(fileExtension);

    // 2 - Преобразование LoadFormat напрямую в его SaveFormat:
    saveFormat = FileFormatUtil.LoadFormatToSaveFormat(loadFormat);

    // Загрузите документ из потока, а затем сохраните его в файле с автоматически обнаруженным расширением.
    Document doc = new Document(docStream);

    Assert.AreEqual(".doc", FileFormatUtil.SaveFormatToExtension(saveFormat));

    doc.Save(ArtifactsDir + "File.SaveToDetectedFileFormat" + FileFormatUtil.SaveFormatToExtension(saveFormat));
}
```

### Смотрите также

* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* пространство имен [Aspose.Words](../../fileformatutil/)
* сборка [Aspose.Words](../../../)


