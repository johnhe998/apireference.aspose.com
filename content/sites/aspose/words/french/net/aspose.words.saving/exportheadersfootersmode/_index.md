---
title: Enum ExportHeadersFootersMode
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.ExportHeadersFootersMode énumération. Spécifie comment les entêtes et pieds de page sont exportés vers HTML MHTML ou EPUB.
type: docs
weight: 4740
url: /fr/net/aspose.words.saving/exportheadersfootersmode/
---
## ExportHeadersFootersMode enumeration

Spécifie comment les en-têtes et pieds de page sont exportés vers HTML, MHTML ou EPUB.

```csharp
public enum ExportHeadersFootersMode
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| None | `0` | Les en-têtes et pieds de page ne sont pas exportés. |
| PerSection | `1` | Les en-têtes et pieds de page principaux sont exportés au début et à la fin de chaque section. |
| FirstSectionHeaderLastSectionFooter | `2` | L'en-tête principal de la première section est exporté au début du document et le pied de page principal est à la fin. |
| FirstPageHeaderFooterPerSection | `3` | L'en-tête et le pied de page de la première page sont exportés au début et à la fin de chaque section. |

### Exemples

Montre comment omettre les en-têtes/pieds de page lors de l'enregistrement d'un document au format HTML.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Ce document contient des en-têtes et des pieds de page. Nous pouvons y accéder via la collection "HeadersFooters".
Assert.AreEqual("First header", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderFirst].GetText().Trim());

// Les formats tels que .html ne divisent pas le document en pages, donc les en-têtes/pieds de page ne fonctionneront pas de la même manière
// ils le feraient lorsque nous ouvrions le document en tant que .docx à l'aide de Microsoft Word.
// Si nous convertissons un document avec des en-têtes/pieds de page en html, la conversion assimilera les en-têtes/pieds de page au corps du texte.
// Nous pouvons utiliser un objet SaveOptions pour omettre les en-têtes/pieds de page lors de la conversion en html.
HtmlSaveOptions saveOptions =
    new HtmlSaveOptions(SaveFormat.Html) { ExportHeadersFootersMode = ExportHeadersFootersMode.None };

doc.Save(ArtifactsDir + "HeaderFooter.ExportMode.html", saveOptions);

// Ouvre notre document enregistré et vérifie qu'il ne contient pas le texte de l'en-tête
doc = new Document(ArtifactsDir + "HeaderFooter.ExportMode.html");

Assert.IsFalse(doc.Range.Text.Contains("First header"));
```

### Voir également

* property [ExportHeadersFootersMode](../htmlsaveoptions/exportheadersfootersmode/)
* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


