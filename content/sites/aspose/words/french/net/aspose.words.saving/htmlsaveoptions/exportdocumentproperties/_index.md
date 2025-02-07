---
title: HtmlSaveOptions.ExportDocumentProperties
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie sil faut exporter les propriétés de document intégrées et personnalisées vers HTML MHTML ou EPUB. La valeur par défaut estfaux .
type: docs
weight: 130
url: /fr/net/aspose.words.saving/htmlsaveoptions/exportdocumentproperties/
---
## HtmlSaveOptions.ExportDocumentProperties property

Spécifie s'il faut exporter les propriétés de document intégrées et personnalisées vers HTML, MHTML ou EPUB. La valeur par défaut est`faux` .

```csharp
public bool ExportDocumentProperties { get; set; }
```

### Exemples

Montre comment utiliser un encodage spécifique lors de l'enregistrement d'un document au format .epub.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Utilisez un objet SaveOptions pour spécifier l'encodage d'un document que nous allons enregistrer.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// Par défaut, un document de sortie .epub aura tout son contenu dans une seule partie HTML.
// Un critère de découpage permet de segmenter le document en plusieurs parties HTML.
// Nous allons définir les critères pour diviser le document en paragraphes d'en-tête.
// Ceci est utile pour les lecteurs qui ne peuvent pas lire les fichiers HTML plus importants qu'une taille spécifique.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// Spécifiez que nous voulons exporter les propriétés du document.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


