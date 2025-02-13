---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie sil faut écrire la déclaration DOCTYPE lors de lenregistrement au format HTML ou MHTML. Lorsquevrai  écrit une déclaration DOCTYPE dans le document avant lélément racine. La valeur par défaut estfaux. Lors de lenregistrement au format EPUB ou HTML5 Html5  la déclaration DOCTYPE est toujours écrite.
type: docs
weight: 290
url: /fr/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

Spécifie s'il faut écrire la déclaration DOCTYPE lors de l'enregistrement au format HTML ou MHTML. Lorsque`vrai` , écrit une déclaration DOCTYPE dans le document avant l'élément racine. La valeur par défaut est`faux`. Lors de l'enregistrement au format EPUB ou HTML5 (Html5 ) la déclaration DOCTYPE est toujours écrite.

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### Remarques

Aspose.Words écrit toujours du HTML bien formé, quel que soit ce paramètre.

Lorsque`vrai`, le début du document de sortie HTML ressemblera à ceci :

Aspose.Words vise à générer du XHTML conformément à la spécification XHTML 1.0 Transitional, , mais la sortie ne sera pas toujours validée par rapport à la DTD. Certaines structures à l'intérieur d'un document Microsoft Word sont difficiles ou impossibles à mapper à un document qui validera par rapport au schéma XHTML. Par exemple, XHTML n'autorise pas les listes imbriquées (UL ne peut pas être imbriquée dans un autre élément UL), mais dans les documents Microsoft Word, les listes à plusieurs niveaux se produisent assez souvent.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="fr" lang="fr">
```

### Exemples

Montre comment afficher un en-tête DOCTYPE lors de la conversion de documents au standard de transition Xhtml 1.0.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = HtmlVersion.Xhtml,
    ExportXhtmlTransitional = showDoctypeDeclaration,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html", options);

// Notre document ne contiendra un en-tête de déclaration DOCTYPE que si nous avons défini le drapeau "ExportXhtmlTransitional" sur "true".
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\">\r\n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\">"));
else
    Assert.True(outDocContents.Contains("<html>"));
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


