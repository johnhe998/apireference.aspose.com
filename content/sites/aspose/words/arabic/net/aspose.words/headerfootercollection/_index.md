---
title: Class HeaderFooterCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.HeaderFooterCollection فصل. توفير وصول مكتوب إلىHeaderFooter العقد من الجزء .
type: docs
weight: 2930
url: /ar/net/aspose.words/headerfootercollection/
---
## HeaderFooterCollection class

توفير وصول مكتوب إلى[`HeaderFooter`](../headerfooter/) العقد من **الجزء** .

```csharp
public class HeaderFooterCollection : NodeCollection
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | الحصول على عدد العقد في المجموعة. |
| [Item](../../aspose.words/headerfootercollection/item/) { get; } | يسترجع أ **تذييل الرأس** في الفهرس المحدد. (3 indexers) |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | يضيف عقدة إلى نهاية المجموعة. |
| [Clear](../../aspose.words/nodecollection/clear/)() | يزيل كافة العقد من هذه المجموعة ومن المستند. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | لتحديد ما إذا كانت العقدة موجودة في المجموعة. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | يوفر تكرارًا بسيطًا لنمط "foreach" عبر مجموعة العقد. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | إرجاع الفهرس الصفري للعقدة المحددة. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | إدراج عقدة في المجموعة بالفهرس المحدد. |
| [LinkToPrevious](../../aspose.words/headerfootercollection/linktoprevious/#linktoprevious_1)(bool) | روابط أو إلغاء ربط كافة الرؤوس والتذييلات بالرؤوس والتذييلات المقابلة في القسم السابق. |
| [LinkToPrevious](../../aspose.words/headerfootercollection/linktoprevious/#linktoprevious)(HeaderFooterType, bool) | ارتباطات أو إلغاء ارتباط الرأس أو التذييل المحدد بالرأس أو التذييل المقابل في القسم السابق. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | يزيل العقدة من المجموعة ومن الوثيقة. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | يزيل العقدة في الفهرس المحدد من المجموعة ومن المستند. |
| [ToArray](../../aspose.words/headerfootercollection/toarray/#toarray)() | نسخ الكل`HeaderFoorter` s من المجموعة إلى مجموعة جديدة من`HeaderFoorter` s. (2 methods) |

### ملاحظات

يمكن أن يكون هناك واحد كحد أقصى **تذييل الرأس**

لكل واحد[`HeaderFooterType`](../headerfootertype/) لكل_  **الجزء** .

**تذييل الرأس** يمكن أن تحدث الكائنات بأي ترتيب في المجموعة.

### أمثلة

يوضح كيفية حذف كل التذييلات من مستند.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// كرر خلال كل قسم وقم بإزالة التذييلات من كل نوع.
foreach (Section section in doc.OfType<Section>())
{
    // هناك ثلاثة أنواع من أنواع التذييل والرأس.
    // 1 - الرأس / التذييل "الأول" ، والذي يظهر فقط في الصفحة الأولى من القسم.
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - الرأس / التذييل "الأساسي" ، والذي يظهر في الصفحات الفردية.
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

     // 3 - رأس / تذييل "زوجي" ، والذي يظهر في الصفحات الزوجية.
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

يوضح كيفية إنشاء رأس وتذييل.

```csharp
Document doc = new Document();

// إنشاء رأس وإلحاق فقرة به. النص في تلك الفقرة
// في أعلى كل صفحة من هذا القسم ، فوق النص الأساسي الرئيسي.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// إنشاء تذييل وإلحاق فقرة به. النص في تلك الفقرة
// في أسفل كل صفحة من هذا القسم ، أسفل النص الأساسي الرئيسي.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### أنظر أيضا

* class [NodeCollection](../nodecollection/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


