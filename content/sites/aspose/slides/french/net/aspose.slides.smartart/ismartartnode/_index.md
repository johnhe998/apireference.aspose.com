---
title: ISmartArtNode
second_title: Référence de l'API Aspose.Slides pour .NET
description: Représente le nœud dun diagramme SmartArt.
type: docs
weight: 9800
url: /fr/net/aspose.slides.smartart/ismartartnode/
---
## ISmartArtNode interface

Représente le nœud d'un diagramme SmartArt.

```csharp
public interface ISmartArtNode
```

## Propriétés

| Nom | La description |
| --- | --- |
| [BulletFillFormat](../../aspose.slides.smartart/ismartartnode/bulletfillformat) { get; } | Renvoie l'objet FillFormat qui contient les propriétés de formatage de remplissage pour une puce de nœud. Remarque : peut renvoyer la valeur null pour certains types de mise en page SmartArt qui ne fournissent pas de puces pour les nœuds. En lecture seule[`IFillFormat`](../../aspose.slides/ifillformat) . |
| [ChildNodes](../../aspose.slides.smartart/ismartartnode/childnodes) { get; } | Renvoie les collections de tous les nœuds enfants du nœud actuel. Lecture seule[`ISmartArtNodeCollection`](../ismartartnodecollection) . |
| [IsAssistant](../../aspose.slides.smartart/ismartartnode/isassistant) { get; set; } | Renvoie ou définit le nœud comme assistant. Lecture/écritureBoolean . |
| [IsHidden](../../aspose.slides.smartart/ismartartnode/ishidden) { get; } | Renvoie vrai si ce nœud est un nœud caché dans le modèle de données. Lecture seuleBoolean . |
| [Level](../../aspose.slides.smartart/ismartartnode/level) { get; } | Renvoie le niveau d'imbrication du nœud. Lecture seuleInt32 . |
| [OrganizationChartLayout](../../aspose.slides.smartart/ismartartnode/organizationchartlayout) { get; set; } | Renvoie ou définit le type de disposition de l'organigramme associé au nœud actuel. Lecture/écriture[`OrganizationChartLayoutType`](../organizationchartlayouttype) . |
| [Position](../../aspose.slides.smartart/ismartartnode/position) { get; set; } | Renvoie ou définit la position de base zéro du nœud parmi les nœuds frères. Lecture/écritureInt32 . |
| [Shapes](../../aspose.slides.smartart/ismartartnode/shapes) { get; } | Renvoie les collections de toutes les formes associées au nœud. Lecture seule[`ISmartArtShapeCollection`](../ismartartshapecollection) . |
| [TextFrame](../../aspose.slides.smartart/ismartartnode/textframe) { get; } | Renvoie ou définit le texte du nœud. Lecture seule[`ITextFrame`](../../aspose.slides/itextframe) . |

## Méthodes

| Nom | La description |
| --- | --- |
| [Remove](../../aspose.slides.smartart/ismartartnode/remove)() | Supprimer le nœud actuel. |

### Voir également

* espace de noms [Aspose.Slides.SmartArt](../../aspose.slides.smartart)
* Assemblée [Aspose.Slides](../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
