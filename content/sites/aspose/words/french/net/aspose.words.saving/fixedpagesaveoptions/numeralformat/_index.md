---
title: FixedPageSaveOptions.NumeralFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: FixedPageSaveOptions propriété. Obtient ou définitNumeralFormat utilisé pour le rendu des chiffres. Les chiffres européens sont utilisés par défaut.
type: docs
weight: 40
url: /fr/net/aspose.words.saving/fixedpagesaveoptions/numeralformat/
---
## FixedPageSaveOptions.NumeralFormat property

Obtient ou définit[`NumeralFormat`](../../numeralformat/) utilisé pour le rendu des chiffres. Les chiffres européens sont utilisés par défaut.

```csharp
public NumeralFormat NumeralFormat { get; set; }
```

### Remarques

Si la valeur de cette propriété est modifiée et que la mise en page est déjà construite alors [`UpdatePageLayout`](../../../aspose.words/document/updatepagelayout/) est invoqué automatiquement pour mettre à jour toute modification.

### Exemples

Montre comment définir le format numérique utilisé lors de l'enregistrement au format PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = new CultureInfo("ar-AR").LCID;
builder.Writeln("1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50, 100");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Définissez la propriété "NumeralFormat" sur "NumeralFormat.ArabicIndic" pour
// utilise les glyphes de la plage U+0660 à U+0669 comme nombres.
// Définissez la propriété "NumeralFormat" sur "NumeralFormat.Context" pour
// recherche les paramètres régionaux pour déterminer le nombre de glyphes à utiliser.
// Définissez la propriété "NumeralFormat" sur "NumeralFormat.EasternArabicIndic" pour
// utilise les glyphes de la plage U+06F0 à U+06F9 comme nombres.
// Définissez la propriété "NumeralFormat" sur "NumeralFormat.European" pour utiliser les chiffres européens.
// Définissez la propriété "NumeralFormat" sur "NumeralFormat.System" pour déterminer le jeu de symboles à partir des paramètres régionaux.
options.NumeralFormat = numeralFormat;

doc.Save(ArtifactsDir + "PdfSaveOptions.SetNumeralFormat.pdf", options);
```

### Voir également

* enum [NumeralFormat](../../numeralformat/)
* class [FixedPageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


