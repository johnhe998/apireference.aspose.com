---
title: NodeImporter.ImportNode
second_title: Aspose.Words for .NET API Referansı
description: NodeImporter yöntem. Bir düğümü bir belgeden diğerine aktarır.
type: docs
weight: 20
url: /tr/net/aspose.words/nodeimporter/importnode/
---
## NodeImporter.ImportNode method

Bir düğümü bir belgeden diğerine aktarır.

```csharp
public Node ImportNode(Node srcNode, bool isImportChildren)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| srcNode | Node | İçe aktarılacak düğüm. |
| isImportChildren | Boolean | Tüm alt düğümleri yinelemeli olarak içe aktarmak için doğru; aksi halde yanlış. |

### Geri dönüş değeri

Klonlanmış, içe aktarılan düğüm. Düğüm, hedef belgeye aittir, ancak üst öğesi yoktur.

### Notlar

Bir düğümü içe aktarmak, içe aktarma belgesine ait kaynak düğümün bir kopyasını oluşturur. Döndürülen düğümün üst öğesi yok. Kaynak düğüm değiştirilmez veya orijinal belgeden kaldırılmaz.

Başka bir belgeden bir düğüm bu belgeye eklenmeden önce içe aktarılmalıdır. İçe aktarma sırasında, stillere ve listelere referanslar gibi belgeye özgü özellikler orijinalden içe aktarılan belgeye çevrilir. Düğüm içe aktarıldıktan sonra, kullanılarak belgedeki uygun yere eklenebilir.[`InsertBefore`](../../compositenode/insertbefore/) veya [`InsertAfter`](../../compositenode/insertafter/).

Kaynak düğüm zaten hedef belgeye aitse, kaynak düğümün derin bir klonu oluşturulur.

### Örnekler

Bir belgenin içeriğinin başka bir belgedeki yer işaretine nasıl ekleneceğini gösterir.

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
/// Belirtilen düğümden sonra bir belgenin içeriğini ekler.
/// </summary>
static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;

        NodeImporter importer =
            new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        // Bölümün gövdesindeki tüm blok düzeyindeki düğümler arasında dolaşın,
        // sonra bir bölümün son boş paragrafı olmayan her düğümü klonlayın ve ekleyin.
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

### Ayrıca bakınız

* class [Node](../../node/)
* class [NodeImporter](../)
* ad alanı [Aspose.Words](../../nodeimporter/)
* toplantı [Aspose.Words](../../../)


