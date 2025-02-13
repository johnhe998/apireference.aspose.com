---
title: Class HyphenationOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Settings.HyphenationOptions classe. Permet de configurer les options de césure des documents.
type: docs
weight: 5500
url: /fr/net/aspose.words.settings/hyphenationoptions/
---
## HyphenationOptions class

Permet de configurer les options de césure des documents.

```csharp
public class HyphenationOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [HyphenationOptions](hyphenationoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [AutoHyphenation](../../aspose.words.settings/hyphenationoptions/autohyphenation/) { get; set; } | Obtient ou définit la valeur déterminant si la césure automatique est activée pour le document. La valeur par défaut de cette propriété est **faux** . |
| [ConsecutiveHyphenLimit](../../aspose.words.settings/hyphenationoptions/consecutivehyphenlimit/) { get; set; } | Obtient ou définit le nombre maximal de lignes consécutives pouvant se terminer par des tirets. La valeur par défaut de cette propriété est 0. |
| [HyphenateCaps](../../aspose.words.settings/hyphenationoptions/hyphenatecaps/) { get; set; } | Obtient ou définit la valeur déterminant si les mots écrits en majuscules sont coupés. La valeur par défaut de cette propriété est **vrai** . |
| [HyphenationZone](../../aspose.words.settings/hyphenationoptions/hyphenationzone/) { get; set; } | Obtient ou définit la distance en 1/20 de point à partir de la marge de droite à l'intérieur de laquelle vous ne voulez pas couper les mots. La valeur par défaut de cette propriété est 360 (0,25 pouce). |

### Exemples

Montre comment configurer la césure automatique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Voir également

* espace de noms [Aspose.Words.Settings](../../aspose.words.settings/)
* Assemblée [Aspose.Words](../../)


