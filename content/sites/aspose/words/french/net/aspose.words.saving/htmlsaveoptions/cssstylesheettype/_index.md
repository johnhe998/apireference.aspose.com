---
title: HtmlSaveOptions.CssStyleSheetType
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie comment les styles CSS Cascading Style Sheet sont exportés vers HTML MHTML ou EPUB. La valeur par défaut estInline pour HTML/MHTML et External pour EPUB.
type: docs
weight: 60
url: /fr/net/aspose.words.saving/htmlsaveoptions/cssstylesheettype/
---
## HtmlSaveOptions.CssStyleSheetType property

Spécifie comment les styles CSS (Cascading Style Sheet) sont exportés vers HTML, MHTML ou EPUB. La valeur par défaut estInline pour HTML/MHTML et External pour EPUB.

```csharp
public CssStyleSheetType CssStyleSheetType { get; set; }
```

### Remarques

L'enregistrement de la feuille de style CSS dans un fichier externe n'est pris en charge que lors de l'enregistrement au format HTML. Lorsque vous exportez vers l'un des formats de conteneur (EPUB ou MHTML) et que vous spécifiez External, le fichier CSS sera encapsulé dans le package de sortie.

### Exemples

Montre comment utiliser les feuilles de style CSS créées par une conversion HTML.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Crée un objet "HtmlFixedSaveOptions", que nous pouvons passer à la méthode "Save" du document
    // pour modifier la façon dont nous convertissons le document en HTML.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Définissez la propriété "CssStylesheetType" sur "CssStyleSheetType.External" pour
    // accompagne un document HTML enregistré d'un fichier de feuille de style CSS externe.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Vous trouverez ci-dessous deux manières de spécifier des répertoires et des noms de fichiers pour les feuilles de style CSS de sortie.
    // 1 - Utilisez la propriété "CssStyleSheetFileName" pour attribuer un nom de fichier à notre feuille de style :
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Utilisez un rappel personnalisé pour nommer notre feuille de style :
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Définit un nom de fichier personnalisé, ainsi que d'autres paramètres pour une feuille de style CSS externe.
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // Nous pouvons accéder à l'intégralité du document source via la propriété "Document".
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### Voir également

* property [CssStyleSheetFileName](../cssstylesheetfilename/)
* enum [CssStyleSheetType](../../cssstylesheettype/)
* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


