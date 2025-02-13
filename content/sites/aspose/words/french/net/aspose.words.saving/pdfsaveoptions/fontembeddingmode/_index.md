---
title: PdfSaveOptions.FontEmbeddingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Spécifie le mode dincorporation des polices.
type: docs
weight: 140
url: /fr/net/aspose.words.saving/pdfsaveoptions/fontembeddingmode/
---
## PdfSaveOptions.FontEmbeddingMode property

Spécifie le mode d'incorporation des polices.

```csharp
public PdfFontEmbeddingMode FontEmbeddingMode { get; set; }
```

### Remarques

La valeur par défaut estEmbedAll.

Ce paramètre ne fonctionne que pour le texte en encodage ANSI (Windows-1252). Si le document contient du texte non-ANSI , les polices correspondantes seront incorporées quel que soit ce paramètre.

La conformité PDF/A et PDF/UA exige que toutes les polices soient intégrées. EmbedAll sera utilisée automatiquement lors de l'enregistrement au format PDF/A et PDF/UA.

### Exemples

Montre comment configurer Aspose.Words pour ignorer l'intégration des polices Arial et Times New Roman dans un document PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" est une police standard et "Courier New" est une police non standard.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Définissez la propriété "EmbedFullFonts" sur "true" pour incorporer chaque glyphe de chaque police incorporée dans le PDF de sortie.
options.EmbedFullFonts = true;

// Définissez la propriété "FontEmbeddingMode" sur "EmbedAll" pour incorporer toutes les polices dans le PDF de sortie.
// Définissez la propriété "FontEmbeddingMode" sur "EmbedNonstandard" pour autoriser uniquement l'incorporation de polices non standard dans le PDF de sortie.
// Définissez la propriété "FontEmbeddingMode" sur "EmbedNone" pour n'incorporer aucune police dans le PDF de sortie.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Voir également

* enum [PdfFontEmbeddingMode](../../pdffontembeddingmode/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


