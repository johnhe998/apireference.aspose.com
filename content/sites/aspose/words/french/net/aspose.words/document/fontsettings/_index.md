---
title: Document.FontSettings
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Obtient ou définit les paramètres de police du document.
type: docs
weight: 140
url: /fr/net/aspose.words/document/fontsettings/
---
## Document.FontSettings property

Obtient ou définit les paramètres de police du document.

```csharp
public FontSettings FontSettings { get; set; }
```

### Remarques

Cette propriété permet de spécifier les paramètres de police par document. Si défini sur null, paramètres de police statiques par défaut [`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) sera utilisé.

La valeur par défaut est nulle.

### Exemples

Montre comment définir les règles de substitution de police.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();

// Les sources de polices par défaut contiennent la première police utilisée par le document.
Assert.AreEqual(1, fontSources.Length);
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// La deuxième police, "Amethysta", n'est pas disponible.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// On peut configurer une table de substitution de polices qui détermine
// quelles polices Aspose.Words utilisera comme substituts pour les polices indisponibles.
// Définir deux polices de substitution pour "Amethysta": "Arvo" et "Courier New".
// Si le premier substitut n'est pas disponible, Aspose.Words tente d'utiliser le deuxième substitut, et ainsi de suite.
doc.FontSettings = new FontSettings();
doc.FontSettings.SubstitutionSettings.TableSubstitution.SetSubstitutes(
    "Amethysta", new[] {"Arvo", "Courier New"});

 // "Amethysta" n'est pas disponible, et la règle de substitution indique que la première police à utiliser comme substitut est "Arvo".
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

 // "Arvo" est également indisponible, mais "Courier New" l'est.
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Courier New"));

// Le document de sortie affichera le texte qui utilise la police "Amethysta" formaté avec "Courier New".
doc.Save(ArtifactsDir + "FontSettings.TableSubstitution.pdf");
```

### Voir également

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


