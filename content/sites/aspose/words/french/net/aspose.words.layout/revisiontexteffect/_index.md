---
title: Enum RevisionTextEffect
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Layout.RevisionTextEffect énumération. Permet de spécifier leffet de décoration pour les révisions du texte du document.
type: docs
weight: 3200
url: /fr/net/aspose.words.layout/revisiontexteffect/
---
## RevisionTextEffect enumeration

Permet de spécifier l'effet de décoration pour les révisions du texte du document.

```csharp
public enum RevisionTextEffect
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| None | `0` | Le contenu révisé n'a pas d'effets spéciaux appliqués. Cela correspond àNoHighlight . |
| Color | `1` | Le contenu révisé est surligné en couleur uniquement. |
| Bold | `2` | Le contenu révisé est mis en gras et en couleur. |
| Italic | `3` | Le contenu révisé est en italique et coloré. |
| Underline | `4` | Le contenu révisé est souligné et coloré. |
| DoubleUnderline | `5` | Le contenu révisé est double souligné et coloré. |
| StrikeThrough | `6` | Le contenu révisé est barré et coloré. |
| DoubleStrikeThrough | `7` | Le contenu révisé est barré deux fois et coloré. |
| Hidden | `8` | Le contenu révisé est masqué. |

### Exemples

Montre comment modifier l'apparence des révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Récupère l'objet RevisionOptions qui contrôle l'apparence des révisions.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Affiche les révisions d'insertion en vert et en italique.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Afficher les révisions de suppression en rouge et en gras.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Le même texte apparaîtra deux fois dans une révision de mouvement :
// une fois au point de départ et une fois à la destination d'arrivée.
// Rendre le texte à la révision d'origine jaune avec un double barré
// et bleu souligné deux fois à la révision déplacée vers.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Afficher les révisions de format en rouge foncé et en gras.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Place une épaisse barre bleu foncé sur le côté gauche de la page à côté des lignes affectées par les révisions.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Affiche les marques de révision et le texte d'origine.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Obtenez le mouvement, la suppression, les révisions de formatage et les commentaires à afficher dans des bulles vertes
// sur le côté droit de la page.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Ces fonctionnalités ne s'appliquent qu'aux formats tels que .pdf ou .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Voir également

* espace de noms [Aspose.Words.Layout](../../aspose.words.layout/)
* Assemblée [Aspose.Words](../../)


