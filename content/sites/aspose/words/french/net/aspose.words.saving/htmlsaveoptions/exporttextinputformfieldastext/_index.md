---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Contrôle la manière dont les champs du formulaire de saisie de texte sont enregistrés au format HTML ou MHTML. La valeur par défaut estfaux .
type: docs
weight: 270
url: /fr/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

Contrôle la manière dont les champs du formulaire de saisie de texte sont enregistrés au format HTML ou MHTML. La valeur par défaut est`faux` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### Remarques

Lorsqu'il est réglé sur`vrai` , exporte les champs du formulaire de saisie de texte sous forme de texte normal. Quand`faux`, exporte les champs de formulaire de saisie de texte Word en tant qu'éléments INPUT au format HTML.

Lors de l'exportation vers EPUB, les champs du formulaire de saisie de texte sont toujours enregistrés en tant que texte en raison des exigences de ce format.

### Exemples

Montre comment spécifier le dossier de stockage des images liées après l'enregistrement au format .html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Définissez une option pour exporter les champs de formulaire en tant que texte brut au lieu d'éléments d'entrée HTML.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


