---
title: Class NodeImporter
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.NodeImporter فصل. يسمح بإجراء الاستيراد المتكرر للعقد بكفاءة من مستند إلى آخر.
type: docs
weight: 3970
url: /ar/net/aspose.words/nodeimporter/
---
## NodeImporter class

يسمح بإجراء الاستيراد المتكرر للعقد بكفاءة من مستند إلى آخر.

```csharp
public class NodeImporter
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [NodeImporter](nodeimporter/#constructor)(DocumentBase, DocumentBase, ImportFormatMode) | يقوم بتهيئة مثيل جديد لملف`NodeImporter` فئة . |
| [NodeImporter](nodeimporter/#constructor_1)(DocumentBase, DocumentBase, ImportFormatMode, ImportFormatOptions) | يقوم بتهيئة مثيل جديد لملف`NodeImporter` فئة . |

## طُرق

| اسم | وصف |
| --- | --- |
| [ImportNode](../../aspose.words/nodeimporter/importnode/)(Node, bool) | يستورد عقدة من وثيقة إلى أخرى. |

### ملاحظات

يوفر Aspose.Words وظائف لسهولة نسخ ونقل الأجزاء بين مستندات Microsoft Word. يُعرف هذا باسم "عقد الاستيراد" . قبل أن تتمكن من إدراج جزء من مستند إلى آخر ، تحتاج إلى "استيراده".

إن أبسط طريقة لاستيراد عقدة هي استخدام ملحق[`ImportNode`](../documentbase/importnode/) طريقة المقدمة من[`DocumentBase`](../documentbase/) هدف.

ومع ذلك ، عندما تحتاج إلى استيراد عقد من مستند إلى آخر عدة مرات ، فمن الأفضل استخدام`NodeImporter` صف دراسي. ال`NodeImporter` تسمح الفئة بتقليل عدد الأنماط والقوائم التي تم إنشاؤها في المستند الوجهة.

يمثل نسخ أو نقل أجزاء من مستند Microsoft Word إلى مستند آخر عددًا_ من التحديات التقنية لشركة Aspose.Words. في مستند Word ، يتم تخزين الأنماط والقائمة بتنسيق بشكل مركزي ، بشكل منفصل عن نص المستند. تشير الفقرات وتشغيلات النص فقط إلى الأنماط بواسطة معرفات داخلية فريدة.

تنشأ التحديات من حقيقة أن الأنماط والقوائم مختلفة في المستندات المختلفة. _ على سبيل المثال ، لنسخ فقرة منسقة بنمط العنوان 1 من مستند إلى آخر ، يجب مراعاة عدد من الأشياء: قرر ما إذا كنت تريد انسخ نمط العنوان 1 من المستند المصدر إلى المستند الوجهة ، واستنساخ الفقرة ، وقم بتحديث الفقرة المستنسخة بحيث تشير إلى نمط العنوان 1 الصحيح في المستند الوجهة. يجب تحليل المراجع (بناءً على style ونمط الفقرة التالي) وربما نسخها أيضًا وما إلى ذلك. _ توجد مشكلات مماثلة عند نسخ فقرات ذات تعداد نقطي أو رقمي لأن Microsoft Word يخزن تعريفات القوائم بشكل منفصل عن النص.

ال`NodeImporter`فئة هي مثل السياق ، الذي يحمل "جداول الترجمة" أثناء الاستيراد. يترجم بشكل صحيح بين الأنماط والقوائم في المصدر و_ المستندات.

### أمثلة

يوضح كيفية إدراج محتويات أحد المستندات في إشارة مرجعية في مستند آخر.

```csharp
[Test]
public void InsertAtBookmark()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("InsertionPoint");
    builder.Write("We will insert a document here: ");
    builder.EndBookmark("InsertionPoint");

    Document docToInsert = new Document();
    builder = new DocumentBuilder(docToInsert);

    builder.Write("Hello world!");

    docToInsert.Save(ArtifactsDir + "NodeImporter.InsertAtMergeField.docx");

    Bookmark bookmark = doc.Range.Bookmarks["InsertionPoint"];
    InsertDocument(bookmark.BookmarkStart.ParentNode, docToInsert);

    Assert.AreEqual("We will insert a document here: " +
                    "\rHello world!", doc.GetText().Trim());
}

/// <summary>
/// يدخل محتويات الوثيقة بعد العقدة المحددة.
/// </summary>
static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;

        NodeImporter importer =
            new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        // حلقة خلال جميع العقد على مستوى الكتلة في جسم القسم ،
        // ثم استنساخ وأدخل كل عقدة ليست آخر فقرة فارغة من القسم.
        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
            foreach (Node srcNode in srcSection.Body)
            {
                if (srcNode.NodeType == NodeType.Paragraph)
                {
                    Paragraph para = (Paragraph)srcNode;
                    if (para.IsEndOfSection && !para.HasChildNodes)
                        continue;
                }

                Node newNode = importer.ImportNode(srcNode, true);

                destinationParent.InsertAfter(newNode, insertionDestination);
                insertionDestination = newNode;
            }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


