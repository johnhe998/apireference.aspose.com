---
title: TextWatermarkOptions.Layout
second_title: Référence de l'API Aspose.Words pour .NET
description: TextWatermarkOptions propriété. Obtient ou définit la disposition du filigrane. La valeur par défaut estDiagonal .
type: docs
weight: 60
url: /fr/net/aspose.words/textwatermarkoptions/layout/
---
## TextWatermarkOptions.Layout property

Obtient ou définit la disposition du filigrane. La valeur par défaut estDiagonal .

```csharp
public WatermarkLayout Layout { get; set; }
```

### Exemples

Montre comment créer un filigrane de texte.

```csharp
Document doc = new Document();

// Ajouter un filigrane en texte brut.
doc.Watermark.SetText("Aspose Watermark");

// Si nous souhaitons modifier la mise en forme du texte en l'utilisant comme filigrane,
// nous pouvons le faire en passant un objet TextWatermarkOptions lors de la création du filigrane.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Nous pouvons supprimer un filigrane d'un document comme celui-ci.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Voir également

* enum [WatermarkLayout](../../watermarklayout/)
* class [TextWatermarkOptions](../)
* espace de noms [Aspose.Words](../../textwatermarkoptions/)
* Assemblée [Aspose.Words](../../../)


