---
title: PageSetup.BorderAlwaysInFront
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Spécifie où la bordure de la page est positionnée par rapport aux textes et objets qui se croisent.
type: docs
weight: 20
url: /fr/net/aspose.words/pagesetup/borderalwaysinfront/
---
## PageSetup.BorderAlwaysInFront property

Spécifie où la bordure de la page est positionnée par rapport aux textes et objets qui se croisent.

```csharp
public bool BorderAlwaysInFront { get; set; }
```

### Exemples

Montre comment créer une bordure à large bande bleue en haut de la première page.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### Voir également

* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


