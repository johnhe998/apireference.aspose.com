---
title: Font.TintAndShade
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Obtient ou définit une valeur double qui éclaircit ou assombrit une couleur.
type: docs
weight: 520
url: /fr/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

Obtient ou définit une valeur double qui éclaircit ou assombrit une couleur.

```csharp
public double TintAndShade { get; set; }
```

### Remarques

Les valeurs autorisées sont comprises entre -1 (la plus sombre) et 1 (la plus claire) pour cette propriété. Zéro (0) est neutre. Tenter de définir cette propriété sur une valeur inférieure à -1 ou supérieure à 1 entraîne unArgumentOutOfRangeException.

La définition de cette propriété pour l'objet Font avec des couleurs non thématiques entraîne unInvalidOperationException.

### Exemples

Montre comment créer et utiliser un style thématique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Crée un style avec les propriétés de police du thème.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


