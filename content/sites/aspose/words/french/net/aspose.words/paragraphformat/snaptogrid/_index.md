---
title: ParagraphFormat.SnapToGrid
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Spécifie si le paragraphe actuel doit utiliser les lignes de grille du document par paramètres de page lors de la mise en page du contenu du paragraphe.
type: docs
weight: 280
url: /fr/net/aspose.words/paragraphformat/snaptogrid/
---
## ParagraphFormat.SnapToGrid property

Spécifie si le paragraphe actuel doit utiliser les lignes de grille du document par paramètres de page lors de la mise en page du contenu du paragraphe.

```csharp
public bool SnapToGrid { get; set; }
```

### Exemples

Montre comment spécifier une limite pour le nombre de lignes que chaque page peut avoir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Activez le pitching, puis utilisez-le pour définir le nombre de lignes par page dans cette section.
// Une taille de police suffisamment grande poussera certaines lignes vers le bas sur la page suivante pour éviter les caractères qui se chevauchent.
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### Voir également

* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


