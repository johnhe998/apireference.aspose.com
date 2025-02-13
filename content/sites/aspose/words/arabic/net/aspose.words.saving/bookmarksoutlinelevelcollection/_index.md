---
title: Class BookmarksOutlineLevelCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.BookmarksOutlineLevelCollection فصل. مجموعة من مستوى مخطط الإشارات المرجعية الفردية .
type: docs
weight: 4590
url: /ar/net/aspose.words.saving/bookmarksoutlinelevelcollection/
---
## BookmarksOutlineLevelCollection class

مجموعة من مستوى مخطط الإشارات المرجعية الفردية .

```csharp
public class BookmarksOutlineLevelCollection : IEnumerable<KeyValuePair<string, int>>
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [BookmarksOutlineLevelCollection](bookmarksoutlinelevelcollection/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.saving/bookmarksoutlinelevelcollection/count/) { get; } | الحصول على عدد العناصر الموجودة في المجموعة. |
| [Item](../../aspose.words.saving/bookmarksoutlinelevelcollection/item/) { get; set; } | الحصول على أو تحديد مستوى مخطط الإشارة المرجعية بواسطة اسم الإشارة المرجعية. (2 indexers) |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words.saving/bookmarksoutlinelevelcollection/add/)(string, int) | إضافة إشارة مرجعية إلى المجموعة . |
| [Clear](../../aspose.words.saving/bookmarksoutlinelevelcollection/clear/)() | يزيل كل العناصر من المجموعة. |
| [Contains](../../aspose.words.saving/bookmarksoutlinelevelcollection/contains/)(string) | لتحديد ما إذا كانت المجموعة تحتوي على إشارة مرجعية بالاسم المحدد. |
| [GetEnumerator](../../aspose.words.saving/bookmarksoutlinelevelcollection/getenumerator/)() |  |
| [IndexOfKey](../../aspose.words.saving/bookmarksoutlinelevelcollection/indexofkey/)(string) | إرجاع الفهرس الصفري للإشارة المرجعية المحددة في المجموعة. |
| [Remove](../../aspose.words.saving/bookmarksoutlinelevelcollection/remove/)(string) | يزيل إشارة مرجعية بالاسم المحدد من المجموعة. |
| [RemoveAt](../../aspose.words.saving/bookmarksoutlinelevelcollection/removeat/)(int) | يزيل إشارة مرجعية في الفهرس المحدد . |

### ملاحظات

المفتاح هو اسم إشارة مرجعية لسلسلة غير حساسة لحالة الأحرف. القيمة هي مستوى مخطط مرجعي int.

قد يكون مستوى مخطط الإشارة المرجعية قيمة من 0 إلى 9. حدد 0 ولن يتم عرض إشارة مرجعية لـ Word في مخطط المستند . حدد 1 وسيتم عرض إشارة مرجعية Word في مخطط المستند في المستوى 1 ؛ 2 للمستوى 2 وما إلى ذلك.

### أمثلة

يوضح كيفية تعيين مستويات المخطط التفصيلي للإشارات المرجعية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل إشارة مرجعية مع إشارة مرجعية أخرى متداخلة بداخلها.
builder.StartBookmark("Bookmark 1");
builder.Writeln("Text inside Bookmark 1.");

builder.StartBookmark("Bookmark 2");
builder.Writeln("Text inside Bookmark 1 and 2.");
builder.EndBookmark("Bookmark 2");

builder.Writeln("Text inside Bookmark 1.");
builder.EndBookmark("Bookmark 1");

// أدخل إشارة مرجعية أخرى.
builder.StartBookmark("Bookmark 3");
builder.Writeln("Text inside Bookmark 3.");
builder.EndBookmark("Bookmark 3");

// عند الحفظ في .pdf ، يمكن الوصول إلى الإشارات المرجعية من خلال القائمة المنسدلة واستخدامها كإرساء من قبل معظم القراء.
// يمكن أن تحتوي الإشارات المرجعية أيضًا على قيم رقمية لمستويات المخطط التفصيلي ،
// تمكين إدخالات المخطط التفصيلي ذات المستوى الأدنى لإخفاء الإدخالات الفرعية ذات المستوى الأعلى عند طيها في القارئ.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
BookmarksOutlineLevelCollection outlineLevels = pdfSaveOptions.OutlineOptions.BookmarksOutlineLevels;

outlineLevels.Add("Bookmark 1", 1);
outlineLevels.Add("Bookmark 2", 2);
outlineLevels.Add("Bookmark 3", 3);

Assert.AreEqual(3, outlineLevels.Count);
Assert.True(outlineLevels.Contains("Bookmark 1"));
Assert.AreEqual(1, outlineLevels[0]);
Assert.AreEqual(2, outlineLevels["Bookmark 2"]);
Assert.AreEqual(2, outlineLevels.IndexOfKey("Bookmark 3"));

// يمكننا إزالة عنصرين بحيث لا يتبقى سوى تعيين مستوى المخطط التفصيلي لـ "الإشارة المرجعية 1".
outlineLevels.RemoveAt(2);
outlineLevels.Remove("Bookmark 2");

// هناك تسعة مستويات للمخطط التفصيلي. سيتم تحسين ترقيمهم أثناء عملية الحفظ.
// في هذه الحالة ، ستصبح المستويات "5" و "9" هي "2" و "3".
outlineLevels.Add("Bookmark 2", 5);
outlineLevels.Add("Bookmark 3", 9);

doc.Save(ArtifactsDir + "BookmarksOutlineLevelCollection.BookmarkLevels.pdf", pdfSaveOptions);

// سيحافظ تفريغ هذه المجموعة على الإشارات المرجعية ويضعها جميعًا في نفس مستوى المخطط التفصيلي.
outlineLevels.Clear();
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


