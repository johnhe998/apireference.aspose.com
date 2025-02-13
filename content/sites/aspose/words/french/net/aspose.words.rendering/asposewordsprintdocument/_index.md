---
title: Class AsposeWordsPrintDocument
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Rendering.AsposeWordsPrintDocument classe. Fournit une implémentation par défaut pour limpression dunDocument dans le framework dimpression .NET.
type: docs
weight: 4280
url: /fr/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Fournit une implémentation par défaut pour l'impression d'un[`Document`](../../aspose.words/document/) dans le framework d'impression .NET.

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | Initialise une nouvelle instance de cette classe. |

## Méthodes

| Nom | La description |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Lit et met en cache certains champs dePrinterSettings pour réduire le temps d'impression. |

### Remarques

`AsposeWordsPrintDocument` remplacePrintEventArgs) pour imprimer la plage de pages spécifiée dansPrinterSettings.

Un seul document Word peut être composé de plusieurs sections qui spécifient des pages avec des tailles, des orientations et des bacs à papier différents.`AsposeWordsPrintDocument` remplace QueryPageSettingsEventArgs) pour sélectionner correctement la taille du papier, l'orientation et la source du papier lors de l'impression d'un document Word.

Microsoft Word stocke des valeurs spécifiques à l'imprimante pour les bacs à papier dans un document Word et, par conséquent, uniquement l'impression sur le même modèle d'imprimante que celui qui a été sélectionné lorsque l'utilisateur a spécifié les bacs à papier entraînera l'impression à partir des bacs corrects. Si vous imprimez un document sur une autre imprimante, alors très probablement le bac à papier par défaut sera utilisé, et non les bacs spécifiés dans le document.

### Voir également

* espace de noms [Aspose.Words.Rendering](../../aspose.words.rendering/)
* Assemblée [Aspose.Words](../../)


