---
title: Class ViewOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Settings.ViewOptions classe. Fournit diverses options qui contrôlent laffichage dun document dans Microsoft Word.
type: docs
weight: 5650
url: /fr/net/aspose.words.settings/viewoptions/
---
## ViewOptions class

Fournit diverses options qui contrôlent l'affichage d'un document dans Microsoft Word.

```csharp
public class ViewOptions
```

## Propriétés

| Nom | La description |
| --- | --- |
| [DisplayBackgroundShape](../../aspose.words.settings/viewoptions/displaybackgroundshape/) { get; set; } | Contrôle l'affichage de la forme d'arrière-plan en mode d'impression. |
| [DoNotDisplayPageBoundaries](../../aspose.words.settings/viewoptions/donotdisplaypageboundaries/) { get; set; } | Désactive l'affichage de l'espace entre le haut du texte et le bord supérieur de la page. |
| [FormsDesign](../../aspose.words.settings/viewoptions/formsdesign/) { get; set; } | Spécifie si le document est en mode création de formulaires. |
| [ViewType](../../aspose.words.settings/viewoptions/viewtype/) { get; set; } | Contrôle le mode d'affichage dans Microsoft Word. |
| [ZoomPercent](../../aspose.words.settings/viewoptions/zoompercent/) { get; set; } | Obtient ou définit le pourcentage (entre 10 et 500) auquel vous souhaitez afficher votre document. |
| [ZoomType](../../aspose.words.settings/viewoptions/zoomtype/) { get; set; } | Obtient ou définit une valeur de zoom basée sur la taille de la fenêtre. |

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

* class [Document](../../aspose.words/document/)
* property [ViewOptions](../../aspose.words/document/viewoptions/)
* espace de noms [Aspose.Words.Settings](../../aspose.words.settings/)
* Assemblée [Aspose.Words](../../)


