---
title: Bookmark.Name
second_title: Aspose.Words لمراجع .NET API
description: Bookmark ملكية. الحصول على اسم الإشارة المرجعية أو تعيينه.
type: docs
weight: 60
url: /ar/net/aspose.words/bookmark/name/
---
## Bookmark.Name property

الحصول على اسم الإشارة المرجعية أو تعيينه.

```csharp
public string Name { get; set; }
```

### ملاحظات

لاحظ أنه إذا قمت بتغيير اسم إشارة مرجعية إلى اسم موجود بالفعل في المستند ، فلن يظهر أي خطأ وسيتم تخزين الإشارة المرجعية الأولى فقط عند حفظ المستند.

### أمثلة

يوضح كيفية إدراج إشارة مرجعية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تحتوي إشارة مرجعية صالحة على اسم و BookmarkStart وعقدة BookmarkEnd.
// سيتم تحويل أي مسافة بيضاء في أسماء الإشارات المرجعية إلى شرطات سفلية إذا فتحنا المستند المحفوظ باستخدام Microsoft Word. 
// إذا قمنا بتمييز اسم الإشارة المرجعية في Microsoft Word عبر Insert - > الروابط - >. ضع إشارة مرجعية واضغط على "الانتقال إلى" ،
// سينتقل المؤشر إلى النص المرفق بين عقدتي BookmarkStart و BookmarkEnd.
builder.StartBookmark("My Bookmark");
builder.Write("Contents of MyBookmark.");
builder.EndBookmark("My Bookmark");

// يتم تخزين الإشارات المرجعية في هذه المجموعة.
Assert.AreEqual("My Bookmark", doc.Range.Bookmarks[0].Name);

doc.Save(ArtifactsDir + "Bookmarks.Insert.docx");
```

يوضح كيفية إضافة الإشارات المرجعية وتحديث محتوياتها.

```csharp
public void CreateUpdateAndPrintBookmarks()
{
    // أنشئ مستندًا بثلاث إشارات مرجعية ، ثم استخدم تنفيذ زائر مستند مخصص لطباعة محتوياتها.
    Document doc = CreateDocumentWithBookmarks(3);
    BookmarkCollection bookmarks = doc.Range.Bookmarks;

    PrintAllBookmarkInfo(bookmarks);

    // يمكن الوصول إلى الإشارات المرجعية في مجموعة الإشارات المرجعية بالفهرس أو الاسم ، ويمكن تحديث أسمائها.
    bookmarks[0].Name = $"{bookmarks[0].Name}_NewName";
    bookmarks["MyBookmark_2"].Text = $"Updated text contents of {bookmarks[1].Name}";

    // طباعة جميع الإشارات المرجعية مرة أخرى لرؤية القيم المحدثة.
    PrintAllBookmarkInfo(bookmarks);
}

/// <summary>
/// أنشئ مستندًا بعدد معين من الإشارات المرجعية.
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
/// استخدم مكررًا وزائرًا لطباعة معلومات كل إشارة مرجعية في المجموعة.
/// </summary>
private static void PrintAllBookmarkInfo(BookmarkCollection bookmarks)
{
    BookmarkInfoPrinter bookmarkVisitor = new BookmarkInfoPrinter();

    // احصل على كل إشارة مرجعية في المجموعة لقبول الزائر الذي سيطبع محتوياتها.
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
/// يطبع محتويات كل إشارة مرجعية تمت زيارتها على وحدة التحكم.
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

### أنظر أيضا

* class [Bookmark](../)
* مساحة الاسم [Aspose.Words](../../bookmark/)
* المجسم [Aspose.Words](../../../)


