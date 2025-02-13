---
title: Font.ItalicBi
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Vrai si le texte de droite à gauche est formaté en italique.
type: docs
weight: 170
url: /fr/net/aspose.words/font/italicbi/
---
## Font.ItalicBi property

Vrai si le texte de droite à gauche est formaté en italique.

```csharp
public bool ItalicBi { get; set; }
```

### Exemples

Montre comment définir des ensembles distincts de paramètres de police pour le texte de droite à gauche et de droite à gauche.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Définit un ensemble de paramètres de police pour le texte de gauche à droite.
builder.Font.Name = "Courier New";
builder.Font.Size = 16;
builder.Font.Italic = false;
builder.Font.Bold = false;
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Définit un autre ensemble de paramètres de police pour le texte de droite à gauche.
builder.Font.NameBi = "Andalus";
builder.Font.SizeBi = 24;
builder.Font.ItalicBi = true;
builder.Font.BoldBi = true;
builder.Font.LocaleIdBi = new CultureInfo("ar-AR", false).LCID;

// Nous pouvons utiliser le drapeau Bidi pour indiquer si le texte que nous sommes sur le point d'ajouter
// avec le générateur de document est de droite à gauche. Lorsque nous ajoutons du texte avec cet indicateur défini sur true,
// il sera formaté en utilisant l'ensemble de paramètres de police de droite à gauche.
builder.Font.Bidi = true;
builder.Write("مرحبًا");

// Définissez l'indicateur sur false, puis ajoutez du texte de gauche à droite.
// Le générateur de document les formatera en utilisant l'ensemble de paramètres de police de gauche à droite.
builder.Font.Bidi = false;
builder.Write(" Hello world!");

doc.Save(ArtifactsDir + "Font.Bidi.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


