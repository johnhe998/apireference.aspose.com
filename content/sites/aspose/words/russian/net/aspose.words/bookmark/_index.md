---
title: Class Bookmark
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Bookmark сорт. Представляет одну закладку.
type: docs
weight: 30
url: /ru/net/aspose.words/bookmark/
---
## Bookmark class

Представляет одну закладку.

```csharp
public class Bookmark
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [BookmarkEnd](../../aspose.words/bookmark/bookmarkend/) { get; } | Получает узел, представляющий конец закладки. |
| [BookmarkStart](../../aspose.words/bookmark/bookmarkstart/) { get; } | Получает узел, представляющий начало закладки. |
| [FirstColumn](../../aspose.words/bookmark/firstcolumn/) { get; } | Получает отсчитываемый от нуля индекс первого столбца диапазона столбцов таблицы, связанного с закладкой. |
| [IsColumn](../../aspose.words/bookmark/iscolumn/) { get; } | Возвращает **истинный** если эта закладка является закладкой столбца таблицы. |
| [LastColumn](../../aspose.words/bookmark/lastcolumn/) { get; } | Получает отсчитываемый от нуля индекс последнего столбца диапазона столбцов таблицы, связанного с закладкой. |
| [Name](../../aspose.words/bookmark/name/) { get; set; } | Получает или задает имя закладки. |
| [Text](../../aspose.words/bookmark/text/) { get; set; } | Получает или задает текст, заключенный в закладку. |

## Методы

| Имя | Описание |
| --- | --- |
| [Remove](../../aspose.words/bookmark/remove/)() | Удаляет закладку из документа. Не удаляет текст внутри закладки. |

### Примечания

`Bookmark` это объект «фасад», который инкапсулирует два узла[`BookmarkStart`](./bookmarkstart/) и[`BookmarkEnd`](./bookmarkend/) в дереве документа и позволяет работать с закладкой как с единым объектом.

### Примеры

Показывает, как добавлять закладки и обновлять их содержимое.

```csharp
public void CreateUpdateAndPrintBookmarks()
{
    // Создайте документ с тремя закладками, затем используйте пользовательскую реализацию посетителя документа для печати их содержимого.
    Document doc = CreateDocumentWithBookmarks(3);
    BookmarkCollection bookmarks = doc.Range.Bookmarks;

    PrintAllBookmarkInfo(bookmarks);

    // Доступ к закладкам в коллекции закладок можно получить по индексу или имени, и их имена можно обновить.
    bookmarks[0].Name = $"{bookmarks[0].Name}_NewName";
    bookmarks["MyBookmark_2"].Text = $"Updated text contents of {bookmarks[1].Name}";

    // Печатаем все закладки еще раз, чтобы увидеть обновленные значения.
    PrintAllBookmarkInfo(bookmarks);
}

/// <summary>
/// Создать документ с заданным количеством закладок.
/// </summary>
private static Document CreateDocumentWithBookmarks(int numberOfBookmarks)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    for (int i = 1; i <= numberOfBookmarks; i++)
    {
        string bookmarkName = "MyBookmark_" + i;

        builder.Write("Text before bookmark.");
        builder.StartBookmark(bookmarkName);
        builder.Write($"Text inside {bookmarkName}.");
        builder.EndBookmark(bookmarkName);
        builder.Writeln("Text after bookmark.");
    }

    return doc;
}

/// <summary>
/// Используйте итератор и посетитель для вывода информации о каждой закладке в коллекции.
/// </summary>
private static void PrintAllBookmarkInfo(BookmarkCollection bookmarks)
{
    BookmarkInfoPrinter bookmarkVisitor = new BookmarkInfoPrinter();

    // Получить каждую закладку в коллекции, чтобы принять посетителя, который распечатает ее содержимое.
    using (IEnumerator<Bookmark> enumerator = bookmarks.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Bookmark currentBookmark = enumerator.Current;

            if (currentBookmark != null)
            {
                currentBookmark.BookmarkStart.Accept(bookmarkVisitor);
                currentBookmark.BookmarkEnd.Accept(bookmarkVisitor);

                Console.WriteLine(currentBookmark.BookmarkStart.GetText());
            }
        }
    }
}

/// <summary>
/// Выводит содержимое каждой посещенной закладки на консоль.
/// </summary>
public class BookmarkInfoPrinter : DocumentVisitor
{
    public override VisitorAction VisitBookmarkStart(BookmarkStart bookmarkStart)
    {
        Console.WriteLine($"BookmarkStart name: \"{bookmarkStart.Name}\", Contents: \"{bookmarkStart.Bookmark.Text}\"");
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitBookmarkEnd(BookmarkEnd bookmarkEnd)
    {
        Console.WriteLine($"BookmarkEnd name: \"{bookmarkEnd.Name}\"");
        return VisitorAction.Continue;
    }
}
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


