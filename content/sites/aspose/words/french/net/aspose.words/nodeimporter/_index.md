---
title: Class NodeImporter
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.NodeImporter classe. Permet deffectuer efficacement des importations répétées de nœuds dun document à un autre.
type: docs
weight: 3970
url: /fr/net/aspose.words/nodeimporter/
---
## NodeImporter class

Permet d'effectuer efficacement des importations répétées de nœuds d'un document à un autre.

```csharp
public class NodeImporter
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [NodeImporter](nodeimporter/#constructor)(DocumentBase, DocumentBase, ImportFormatMode) | Initialise une nouvelle instance du`NodeImporter` classe. |
| [NodeImporter](nodeimporter/#constructor_1)(DocumentBase, DocumentBase, ImportFormatMode, ImportFormatOptions) | Initialise une nouvelle instance du`NodeImporter` classe. |

## Méthodes

| Nom | La description |
| --- | --- |
| [ImportNode](../../aspose.words/nodeimporter/importnode/)(Node, bool) | Importe un nœud d'un document dans un autre. |

### Remarques

Aspose.Words fournit des fonctionnalités permettant de copier et de déplacer facilement des fragments entre des documents Microsoft Word. C'est ce qu'on appelle "l'importation de nœuds". Avant de pouvoir insérer un fragment d'un document dans un autre, vous devez l'"importer". L'importation crée un clone profond du nœud d'origine, prêt à être inséré dans le document de destination.

La façon la plus simple d'importer un nœud est d'utiliser le[`ImportNode`](../documentbase/importnode/) method fourni par le[`DocumentBase`](../documentbase/) objet.

Cependant, lorsque vous devez importer plusieurs fois des nœuds d'un document à un autre, il est préférable d'utiliser le`NodeImporter` classer. La`NodeImporter` La classe permet de minimiser le nombre de styles et de listes créés dans le document de destination.

Copier ou déplacer des fragments d'un document Microsoft Word à un autre présente un nombre de défis techniques pour Aspose.Words. Dans un document Word, les styles et le formatage de liste sont stockés de manière centralisée, séparément du texte du document. Les paragraphes et les séquences de texte font simplement référence aux styles par des identifiants internes uniques.

Les défis proviennent du fait que les styles et les listes sont différents dans différents documents. Par exemple, pour copier un paragraphe formaté avec le style Titre 1 d'un document à un autre, un certain nombre de choses doivent être prises en compte : décider si copiez le style Titre 1 de du document source vers le document de destination, clonez le paragraphe, mettez à jour le paragraphe cloné afin qu'il fasse référence au style Titre 1 correct dans le document de destination. Si le style devait être copié, tous les styles qu'il les références (basées sur le style et le style de paragraphe suivant) doivent être analysées et éventuellement copiées également, etc. Des problèmes similaires existent lors de la copie de paragraphes à puces ou numérotés, car Microsoft Word stocke les définitions de liste séparément du texte.

La`NodeImporter`class est comme un contexte, qui contient les "tables de traduction" lors de l'importation. Il traduit correctement entre les styles et les listes dans les documents source et destination.

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

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


