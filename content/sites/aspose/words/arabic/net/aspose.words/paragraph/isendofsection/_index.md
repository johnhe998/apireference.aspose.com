---
title: Paragraph.IsEndOfSection
second_title: Aspose.Words لمراجع .NET API
description: Paragraph ملكية. صحيح إذا كانت هذه الفقرة هي الفقرة الأخيرة في ملف الجسم قصة النص الرئيسي من أ الجزء  خطأ بخلاف ذلك.
type: docs
weight: 80
url: /ar/net/aspose.words/paragraph/isendofsection/
---
## Paragraph.IsEndOfSection property

صحيح إذا كانت هذه الفقرة هي الفقرة الأخيرة في ملف **الجسم** (قصة النص الرئيسي) من أ **الجزء** ؛ خطأ بخلاف ذلك.

```csharp
public bool IsEndOfSection { get; }
```

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

* class [Paragraph](../)
* مساحة الاسم [Aspose.Words](../../paragraph/)
* المجسم [Aspose.Words](../../../)


