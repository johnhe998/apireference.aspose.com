---
title: ViewOptions.ZoomType
second_title: Référence de l'API Aspose.Words pour .NET
description: ViewOptions propriété. Obtient ou définit une valeur de zoom basée sur la taille de la fenêtre.
type: docs
weight: 60
url: /fr/net/aspose.words.settings/viewoptions/zoomtype/
---
## ViewOptions.ZoomType property

Obtient ou définit une valeur de zoom basée sur la taille de la fenêtre.

```csharp
public ZoomType ZoomType { get; set; }
```

### Exemples

Montre comment définir un facteur de zoom personnalisé, que les anciennes versions de Microsoft Word appliqueront à un document lors du chargement.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

Montre comment définir un type de zoom personnalisé, que les anciennes versions de Microsoft Word appliqueront à un document lors du chargement.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Définissez la propriété "ZoomType" sur "ZoomType.PageWidth" pour obtenir Microsoft Word
// pour zoomer automatiquement le document pour l'adapter à la largeur de la page.
// Définissez la propriété "ZoomType" sur "ZoomType.FullPage" pour obtenir Microsoft Word
// pour zoomer automatiquement le document afin de rendre visible toute la première page.
// Définissez la propriété "ZoomType" sur "ZoomType.TextFit" pour obtenir Microsoft Word
// pour agrandir automatiquement le document afin qu'il corresponde aux marges intérieures du texte de la première page.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Voir également

* enum [ZoomType](../../zoomtype/)
* class [ViewOptions](../)
* espace de noms [Aspose.Words.Settings](../../viewoptions/)
* Assemblée [Aspose.Words](../../../)


