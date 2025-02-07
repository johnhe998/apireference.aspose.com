---
title: PageSetup.BorderDistanceFrom
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Obtient ou définit une valeur qui indique si la bordure de page spécifiée est mesurée à partir du bord de la page ou du texte quelle entoure.
type: docs
weight: 40
url: /fr/net/aspose.words/pagesetup/borderdistancefrom/
---
## PageSetup.BorderDistanceFrom property

Obtient ou définit une valeur qui indique si la bordure de page spécifiée est mesurée à partir du bord de la page ou du texte qu'elle entoure.

```csharp
public PageBorderDistanceFrom BorderDistanceFrom { get; set; }
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

* enum [PageBorderDistanceFrom](../../pageborderdistancefrom/)
* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


