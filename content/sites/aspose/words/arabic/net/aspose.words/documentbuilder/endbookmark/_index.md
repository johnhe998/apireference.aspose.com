---
title: DocumentBuilder.EndBookmark
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. وضع علامة على الموضع الحالي في المستند كنهاية إشارة مرجعية.
type: docs
weight: 190
url: /ar/net/aspose.words/documentbuilder/endbookmark/
---
## DocumentBuilder.EndBookmark method

وضع علامة على الموضع الحالي في المستند كنهاية إشارة مرجعية.

```csharp
public BookmarkEnd EndBookmark(string bookmarkName)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| bookmarkName | String | اسم المرجعية. |

### قيمة الإرجاع

عقدة نهاية الإشارة التي تم إنشاؤها للتو.

### ملاحظات

يمكن أن تتداخل الإشارات المرجعية في المستند وتمتد إلى أي نطاق. لإنشاء إشارة مرجعية صالحة ، تحتاج إلى الاتصال بكليهما[`StartBookmark`](../startbookmark/) و`EndBookmark` مع نفس الشيء **اسم العلامة** المعلمة.

سيتم تجاهل الإشارات المرجعية المكونة بشكل سيئ أو الإشارات المرجعية ذات الأسماء المكررة عند حفظ المستند.

### أمثلة

يوضح كيفية إنشاء إشارة مرجعية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يجب أن تحتوي الإشارة المرجعية الصالحة على نص أساسي للمستند محاطًا به
// تم إنشاء عقدتي BookmarkStart و BookmarkEnd باستخدام اسم إشارة مرجعية مطابق.
builder.StartBookmark("MyBookmark");
builder.Writeln("Hello world!");
builder.EndBookmark("MyBookmark");

Assert.AreEqual(1, doc.Range.Bookmarks.Count);
Assert.AreEqual("MyBookmark", doc.Range.Bookmarks[0].Name);
Assert.AreEqual("Hello world!", doc.Range.Bookmarks[0].Text.Trim());
```

يوضح كيفية إدراج ارتباط تشعبي يشير إلى إشارة مرجعية محلية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("Bookmark1");
builder.Write("Bookmarked text. ");
builder.EndBookmark("Bookmark1");
builder.Writeln("Text outside of the bookmark.");

// أدخل حقل HYPERLINK الذي يرتبط بالإشارة المرجعية. يمكننا تمرير مفاتيح المجال
// إلى طريقة "InsertHyperlink" كجزء من الوسيطة التي تحتوي على اسم الإشارة المرجعية المشار إليها.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Link to Bookmark1", @"Bookmark1"" \o ""Hyperlink Tip", true);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlinkToLocalBookmark.docx");
```

### أنظر أيضا

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


