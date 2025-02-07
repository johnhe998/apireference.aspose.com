---
title: Paragraph.IsInsertRevision
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph propriété. Renvoie true si cet objet a été inséré dans Microsoft Word alors que le suivi des modifications était activé.
type: docs
weight: 110
url: /fr/net/aspose.words/paragraph/isinsertrevision/
---
## Paragraph.IsInsertRevision property

Renvoie true si cet objet a été inséré dans Microsoft Word alors que le suivi des modifications était activé.

```csharp
public bool IsInsertRevision { get; }
```

### Exemples

Montre comment travailler avec des paragraphes de révision.

```csharp
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Les paragraphes ci-dessus ne sont pas des révisions.
// Les paragraphes que nous ajoutons après le démarrage du suivi des révisions seront enregistrés en tant que révisions "Insérer".
doc.StartTrackRevisions("John Doe", DateTime.Now);

para = body.AppendParagraph("Paragraph 4. ");

Assert.True(para.IsInsertRevision);

// Les paragraphes que nous supprimons après avoir démarré le suivi des révisions seront enregistrés en tant que révisions "Supprimer".
ParagraphCollection paragraphs = body.Paragraphs;

Assert.AreEqual(4, paragraphs.Count);

para = paragraphs[2];
para.Remove();

// Ces paragraphes resteront jusqu'à ce que nous acceptions ou rejetions la révision de suppression.
// Accepter la révision supprimera définitivement le paragraphe,
// et rejeter la révision la laissera dans le document comme si nous ne l'avions jamais supprimée.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Acceptez la révision, puis vérifiez que le paragraphe a disparu.
doc.AcceptAllRevisions();

Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
Assert.AreEqual(
    "Paragraph 1. \r" +
    "Paragraph 2. \r" +
    "Paragraph 4.", doc.GetText().Trim());
```

### Voir également

* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


