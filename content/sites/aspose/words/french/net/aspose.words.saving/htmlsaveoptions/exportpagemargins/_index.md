---
title: HtmlSaveOptions.ExportPageMargins
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie si les marges de la page sont exportées vers HTML MHTML ou EPUB. La valeur par défaut estfaux .
type: docs
weight: 220
url: /fr/net/aspose.words.saving/htmlsaveoptions/exportpagemargins/
---
## HtmlSaveOptions.ExportPageMargins property

Spécifie si les marges de la page sont exportées vers HTML, MHTML ou EPUB. La valeur par défaut est`faux` .

```csharp
public bool ExportPageMargins { get; set; }
```

### Remarques

Aspose.Words n'affiche pas la zone des marges de page par défaut. Si des éléments sont complètement ou partiellement coupés par le bord du document, la zone affichée peut être étendue avec cette option.

### Exemples

Montre comment afficher les objets hors limites dans les documents HTML de sortie.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utilise un générateur pour insérer une forme sans habillage.
Shape shape = builder.InsertShape(ShapeType.Cube, 200, 200);

shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.WrapType = WrapType.None;

// Des valeurs de position de forme négatives peuvent placer la forme en dehors des limites de la page.
// Si nous exportons ceci au format HTML, la forme apparaîtra tronquée.
shape.Left = -150;

// Lors de l'enregistrement du document au format HTML, nous pouvons passer un objet SaveOptions
// pour décider s'il faut ajuster la page pour afficher entièrement les objets hors limites.
// Si nous définissons le drapeau "ExportPageMargins" sur "true", la forme sera entièrement visible dans le HTML de sortie.
// Si nous définissons le drapeau "ExportPageMargins" sur "false",
// notre document affichera la forme tronquée comme nous le verrions dans Microsoft Word.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageMargins = exportPageMargins };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html");

if (exportPageMargins)
{
    Assert.True(outDocContents.Contains("<style type=\"text/css\">div.Section1 { margin:70.85pt }</style>"));
    Assert.True(outDocContents.Contains("<div class=\"Section1\"><p style=\"margin-top:0pt; margin-left:151pt; margin-bottom:0pt\">"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));
    Assert.True(outDocContents.Contains("<div><p style=\"margin-top:0pt; margin-left:221.85pt; margin-bottom:0pt\">"));
}
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


