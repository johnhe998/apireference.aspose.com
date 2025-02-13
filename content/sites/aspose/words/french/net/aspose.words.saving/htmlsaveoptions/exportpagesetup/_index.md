---
title: HtmlSaveOptions.ExportPageSetup
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie si la mise en page est exportée vers HTML MHTML ou EPUB. La valeur par défaut estfaux .
type: docs
weight: 230
url: /fr/net/aspose.words.saving/htmlsaveoptions/exportpagesetup/
---
## HtmlSaveOptions.ExportPageSetup property

Spécifie si la mise en page est exportée vers HTML, MHTML ou EPUB. La valeur par défaut est`faux` .

```csharp
public bool ExportPageSetup { get; set; }
```

### Remarques

Chaque[`Section`](../../../aspose.words/section/) dans le modèle de document Aspose.Words fournit des informations de configuration de page via[`PageSetup`](../../../aspose.words/pagesetup/) classer. Lorsque vous exportez un document au format HTML, vous devrez peut-être conserver ces informations pour une utilisation ultérieure. En particulier, la mise en page peut être importante pour le rendu sur un support paginé (impression) ou la conversion ultérieure vers les formats de fichier Microsoft Word natifs (DOCX, DOC, RTF, WML).

Dans la plupart des cas, HTML est destiné à être affiché dans des navigateurs où la pagination n'est pas effectuée. Donc cette feature est inactive par défaut.

### Exemples

Montre comment décider de conserver les informations sur la structure de la section/la configuration de la page lors de l'enregistrement au format HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TopMargin = 36.0;
pageSetup.BottomMargin = 36.0;
pageSetup.PaperSize = PaperSize.A5;

// Lors de l'enregistrement du document au format HTML, nous pouvons passer un objet SaveOptions
// pour décider de conserver ou de supprimer les paramètres de configuration de la page.
// Si nous définissons le drapeau "ExportPageSetup" sur "true", le document HTML de sortie contiendra notre configuration de mise en page.
// Si nous définissons le drapeau "ExportPageSetup" sur "false", l'opération de sauvegarde supprimera nos paramètres de configuration de page
// pour la première section, et les deux sections seront identiques.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageSetup = exportPageSetup };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html");

if (exportPageSetup)
{
    Assert.True(outDocContents.Contains(
        "<style type=\"text/css\">" +
            "@page Section1 { size:419.55pt 595.3pt; margin:36pt 70.85pt }" +
            "@page Section2 { size:612pt 792pt; margin:70.85pt }" +
            "div.Section1 { page:Section1 }div.Section2 { page:Section2 }" +
        "</style>"));

    Assert.True(outDocContents.Contains(
        "<div class=\"Section1\">" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));

    Assert.True(outDocContents.Contains(
        "<div>" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


