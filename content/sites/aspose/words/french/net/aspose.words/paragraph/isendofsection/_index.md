---
title: Paragraph.IsEndOfSection
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph propriété. Vrai si ce paragraphe est le dernier paragraphe de la Corps histoire du texte principal dun Section  faux sinon.
type: docs
weight: 80
url: /fr/net/aspose.words/paragraph/isendofsection/
---
## Paragraph.IsEndOfSection property

Vrai si ce paragraphe est le dernier paragraphe de la **Corps** (histoire du texte principal) d'un **Section** ; faux sinon.

```csharp
public bool IsEndOfSection { get; }
```

### Exemples

Montre comment insérer le contenu d'un document dans un signet d'un autre document.

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
/// Insère le contenu d'un document après le nœud spécifié.
/// </summary>
static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;

        NodeImporter importer =
            new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        // Boucle sur tous les nœuds de niveau bloc dans le corps de la section,
        // puis clonez et insérez chaque nœud qui n'est pas le dernier paragraphe vide d'une section.
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

### Voir également

* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


