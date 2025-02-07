---
title: HtmlFixedSaveOptions.ExportFormFields
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlFixedSaveOptions propriété. Obtient ou définit une indication indiquant si les champs de formulaire sont exportés en tant quéléments interactifs en tant que balise input plutôt que convertis en texte ou en graphiques.
type: docs
weight: 80
url: /fr/net/aspose.words.saving/htmlfixedsaveoptions/exportformfields/
---
## HtmlFixedSaveOptions.ExportFormFields property

Obtient ou définit une indication indiquant si les champs de formulaire sont exportés en tant qu'éléments interactifs (en tant que balise 'input') plutôt que convertis en texte ou en graphiques.

```csharp
public bool ExportFormFields { get; set; }
```

### Exemples

Montre comment exporter des champs de formulaire vers Html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", false, 15);

// Lorsque nous exportons un document avec des champs de formulaire vers .html,
// Aspose.Words peut exporter les champs de formulaire de deux manières.
// Définir le drapeau "ExportFormFields" sur "true" les exportera en tant qu'objets interactifs.
// Définir cet indicateur sur "false" affichera les champs du formulaire en texte brut.
// Cela va les figer à leur valeur actuelle, et empêcher le lecteur de notre document HTML
// de pouvoir interagir avec eux.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportFormFields = exportFormFields
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html");

if (exportFormFields)
{
    Assert.True(Regex.Match(outDocContents,
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<input style=\"position:absolute; left:0pt; top:0pt;\" type=\"checkbox\" name=\"CheckBox\" />").Success);
}
else
{
    Assert.True(Regex.Match(outDocContents, 
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<div class=\"awdiv\" style=\"left:0.8pt; top:0.8pt; width:14.25pt; height:14.25pt; border:solid 0.75pt #000000;\"").Success);
}
```

### Voir également

* class [HtmlFixedSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Assemblée [Aspose.Words](../../../)


