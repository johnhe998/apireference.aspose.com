---
title: PdfLoadOptions.SkipPdfImages
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfLoadOptions propriété. Obtient ou définit lindicateur indiquant si les images doivent être ignorées lors du chargement du document PDF. La valeur par défaut est False.
type: docs
weight: 40
url: /fr/net/aspose.words.loading/pdfloadoptions/skippdfimages/
---
## PdfLoadOptions.SkipPdfImages property

Obtient ou définit l'indicateur indiquant si les images doivent être ignorées lors du chargement du document PDF. La valeur par défaut est False.

```csharp
public bool SkipPdfImages { get; set; }
```

### Exemples

Montre comment ignorer des images lors du chargement de fichiers PDF.

```csharp
PdfLoadOptions options = new PdfLoadOptions();
options.SkipPdfImages = isSkipPdfImages;

Document doc = new Document(MyDir + "Images.pdf", options);
NodeCollection shapeCollection = doc.GetChildNodes(NodeType.Shape, true);

if (isSkipPdfImages)
{
    Assert.AreEqual(shapeCollection.Count, 0);
}
else
{
    Assert.AreNotEqual(shapeCollection.Count, 0);
}
```

### Voir également

* class [PdfLoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../pdfloadoptions/)
* Assemblée [Aspose.Words](../../../)


