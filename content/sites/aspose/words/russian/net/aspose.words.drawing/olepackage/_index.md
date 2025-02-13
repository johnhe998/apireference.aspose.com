---
title: Class OlePackage
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.OlePackage сорт. Позволяет получить доступ к свойствам пакета OLE.
type: docs
weight: 1030
url: /ru/net/aspose.words.drawing/olepackage/
---
## OlePackage class

Позволяет получить доступ к свойствам пакета OLE.

```csharp
public class OlePackage
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [DisplayName](../../aspose.words.drawing/olepackage/displayname/) { get; set; } | Получает или задает отображаемое имя пакета OLE. |
| [FileName](../../aspose.words.drawing/olepackage/filename/) { get; set; } | Получает или задает имя файла пакета OLE. |

### Примечания

Пакет OLE — это устаревший и «недокументированный» способ хранения внедренного объекта, если обработчик OLE неизвестен. . Теперь это приложение исключено из Windows, но MS Word и другие приложения по-прежнему используют его для встраивания данных, если обработчик OLE отсутствует или неизвестен.

### Примеры

Показывает, как вставить объект OLE в документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Объекты OLE позволяют нам открывать другие файлы в локальной файловой системе с помощью другого установленного приложения
// в нашей операционной системе, дважды щелкнув фигуру, содержащую объект OLE в теле документа.
// В этом случае наш внешний файл будет ZIP-архивом.
byte[] zipFileBytes = File.ReadAllBytes(DatabaseDir + "cat001.zip");

using (MemoryStream stream = new MemoryStream(zipFileBytes))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);

    shape.OleFormat.OlePackage.FileName = "Package file name.zip";
    shape.OleFormat.OlePackage.DisplayName = "Package display name.zip";
}

doc.Save(ArtifactsDir + "Shape.InsertOlePackage.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


