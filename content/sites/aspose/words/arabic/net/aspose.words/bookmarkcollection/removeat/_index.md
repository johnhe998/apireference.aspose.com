---
title: BookmarkCollection.RemoveAt
second_title: Aspose.Words لمراجع .NET API
description: BookmarkCollection طريقة. يزيل إشارة مرجعية في الفهرس المحدد .
type: docs
weight: 60
url: /ar/net/aspose.words/bookmarkcollection/removeat/
---
## BookmarkCollection.RemoveAt method

يزيل إشارة مرجعية في الفهرس المحدد .

```csharp
public void RemoveAt(int index)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| index | Int32 | الفهرس الصفري للإشارة المرجعية المراد إزالتها. |

### أمثلة

يوضح كيفية إزالة الإشارات المرجعية من مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل خمس إشارات مرجعية مع نص داخل حدودها.
for (int i = 1; i <= 5; i++)
{
    string bookmarkName = "MyBookmark_" + i;

    builder.StartBookmark(bookmarkName);
    builder.Write($"Text inside {bookmarkName}.");
    builder.EndBookmark(bookmarkName);
    builder.InsertBreak(BreakType.ParagraphBreak);
}

// هذه المجموعة تخزن الإشارات المرجعية.
BookmarkCollection bookmarks = doc.Range.Bookmarks;

Assert.AreEqual(5, bookmarks.Count);

// هناك عدة طرق لإزالة الإشارات المرجعية.
// 1 - استدعاء طريقة إزالة الإشارة المرجعية:
bookmarks["MyBookmark_1"].Remove();

Assert.False(bookmarks.Any(b => b.Name == "MyBookmark_1"));

// 2 - تمرير الإشارة المرجعية إلى طريقة إزالة المجموعة:
Bookmark bookmark = doc.Range.Bookmarks[0];
doc.Range.Bookmarks.Remove(bookmark);

Assert.False(bookmarks.Any(b => b.Name == "MyBookmark_2"));

// 3 - إزالة إشارة مرجعية من المجموعة بالاسم:
doc.Range.Bookmarks.Remove("MyBookmark_3");

Assert.False(bookmarks.Any(b => b.Name == "MyBookmark_3"));

// 4 - إزالة إشارة مرجعية من فهرس في مجموعة الإشارات المرجعية:
doc.Range.Bookmarks.RemoveAt(0);

Assert.False(bookmarks.Any(b => b.Name == "MyBookmark_4"));

// يمكننا مسح مجموعة الإشارات المرجعية بأكملها.
bookmarks.Clear();

// لا يزال النص الموجود داخل الإشارات المرجعية موجودًا في المستند.
Assert.That(bookmarks, Is.Empty);
Assert.AreEqual("Text inside MyBookmark_1.\r" +
                "Text inside MyBookmark_2.\r" +
                "Text inside MyBookmark_3.\r" +
                "Text inside MyBookmark_4.\r" +
                "Text inside MyBookmark_5.", doc.GetText().Trim());
```

### أنظر أيضا

* class [BookmarkCollection](../)
* مساحة الاسم [Aspose.Words](../../bookmarkcollection/)
* المجسم [Aspose.Words](../../../)


