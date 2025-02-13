---
title: HtmlFixedSaveOptions.ExportEmbeddedCss
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlFixedSaveOptions propriété. Spécifie si le CSS Cascading Style Sheet doit être intégré dans le document Html.
type: docs
weight: 40
url: /fr/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedcss/
---
## HtmlFixedSaveOptions.ExportEmbeddedCss property

Spécifie si le CSS (Cascading Style Sheet) doit être intégré dans le document Html.

```csharp
public bool ExportEmbeddedCss { get; set; }
```

### Exemples

Montre comment déterminer où stocker les feuilles de style CSS lors de l'exportation d'un document vers Html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Lorsque nous exportons un document au format HTML, Aspose.Words créera également une feuille de style CSS pour formater le document avec.
// Définir le drapeau "ExportEmbeddedCss" sur "true" enregistrer la feuille de style CSS dans un fichier .css,
// et créez un lien vers le fichier à partir du document html à l'aide d'un <lien> élément.
// Définir le drapeau sur "false" intégrera la feuille de style CSS dans le document Html,
// qui créera un seul fichier au lieu de deux.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = exportEmbeddedCss
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html");

if (exportEmbeddedCss)
{
    Assert.True(Regex.Match(outDocContents, "<style type=\"text/css\">").Success);
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "<link rel=\"stylesheet\" type=\"text/css\" href=\"HtmlFixedSaveOptions[.]ExportEmbeddedCss/styles[.]css\" media=\"all\" />").Success);
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
```

### Voir également

* class [HtmlFixedSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Assemblée [Aspose.Words](../../../)


