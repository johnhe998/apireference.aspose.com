---
title: Class FileCorruptedException
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.FileCorruptedException сорт. Возникает во время загрузки документа когда документ кажется поврежденным и его невозможно загрузить.
type: docs
weight: 2620
url: /ru/net/aspose.words/filecorruptedexception/
---
## FileCorruptedException class

Возникает во время загрузки документа, когда документ кажется поврежденным и его невозможно загрузить.

```csharp
public class FileCorruptedException : Exception
```

### Примеры

Показывает, как перехватывать исключение FileCorruptedException.

```csharp
try
{
    // Если мы получаем сообщение об ошибке «Нечитаемое содержимое» при попытке открыть документ с помощью Microsoft Word,
    // есть вероятность, что мы получим исключение при попытке загрузить этот документ с помощью Aspose.Words.
    Document doc = new Document(MyDir + "Corrupted document.docx");
}
catch (FileCorruptedException e)
{
    Console.WriteLine(e.Message);
}
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


