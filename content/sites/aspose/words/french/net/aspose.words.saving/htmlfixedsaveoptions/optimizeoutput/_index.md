---
title: HtmlFixedSaveOptions.OptimizeOutput
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlFixedSaveOptions propriété. Indicateur indique sil est nécessaire doptimiser la sortie. Si cet indicateur est défini les canevas imbriqués redondants et les canevas vides sont supprimés également les glyphes voisins avec le même formatage sont concaténés. Remarque  La précision de laffichage du contenu peut être affectée si cette propriété est définie sur true. La valeur par défaut est true.
type: docs
weight: 100
url: /fr/net/aspose.words.saving/htmlfixedsaveoptions/optimizeoutput/
---
## HtmlFixedSaveOptions.OptimizeOutput property

Indicateur indique s'il est nécessaire d'optimiser la sortie. Si cet indicateur est défini, les canevas imbriqués redondants et les canevas vides sont supprimés, également les glyphes voisins avec le même formatage sont concaténés. Remarque : La précision de l'affichage du contenu peut être affectée si cette propriété est définie sur true. La valeur par défaut est true.

```csharp
public override bool OptimizeOutput { get; set; }
```

### Exemples

Montre comment simplifier un document lors de son enregistrement au format HTML en supprimant divers objets redondants.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { OptimizeOutput = optimizeOutput };

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html", saveOptions);

// La taille de la version optimisée du document est presque un tiers de la taille du document non optimisé.
Assert.AreEqual(optimizeOutput ? 62521 : 191770,
    new FileInfo(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html").Length, 200);
```

### Voir également

* class [HtmlFixedSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Assemblée [Aspose.Words](../../../)


