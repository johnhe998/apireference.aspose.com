---
title: InsertAutoShape
second_title: Référence de l'API Aspose.Slides pour .NET
description: Crée une nouvelle forme automatique lajuste à partir du modèle par défaut et linsère dans la collection à lindex spécifié. Remarque  le type de la forme sera déterminé par le paramètre shapeType.
type: docs
weight: 250
url: /fr/net/aspose.slides/ishapecollection/insertautoshape/
---
## InsertAutoShape(int, ShapeType, float, float, float, float) {#insertautoshape}

Crée une nouvelle forme automatique, l'ajuste à partir du modèle par défaut et l'insère dans la collection à l'index spécifié. Remarque : le type de la forme sera déterminé par le paramètre shapeType.

```csharp
public IAutoShape InsertAutoShape(int index, ShapeType shapeType, float x, float y, float width, 
    float height)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| index | Int32 | Index de base zéro auquel la valeur doit être insérée. |
| shapeType | ShapeType | Un[`ShapeType`](../../shapetype) de forme. |
| x | Single | Coordonnée X d'un côté gauche du cadre de la forme. |
| y | Single | Coordonnée Y d'un côté supérieur du cadre de la forme. |
| width | Single | La largeur du cadre de la forme. |
| height | Single | La hauteur du cadre de la forme. |

### Return_Value

Objet AutoShape créé.

### Voir également

* interface [IAutoShape](../../iautoshape)
* enum [ShapeType](../../shapetype)
* interface [IShapeCollection](../../ishapecollection)
* espace de noms [Aspose.Slides](../../ishapecollection)
* Assemblée [Aspose.Slides](../../../)

---

## InsertAutoShape(int, ShapeType, float, float, float, float, bool) {#insertautoshape_1}

Crée une nouvelle forme automatique et l'insère dans la collection à l'index spécifié. Remarque : le type de la forme sera déterminé par le paramètre shapeType.

```csharp
public IAutoShape InsertAutoShape(int index, ShapeType shapeType, float x, float y, float width, 
    float height, bool createFromTemplate)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| index | Int32 | Index de base zéro auquel la valeur doit être insérée. |
| shapeType | ShapeType | Un[`ShapeType`](../../shapetype) de forme. |
| x | Single | Coordonnée X d'un côté gauche du cadre de la forme. |
| y | Single | Coordonnée Y d'un côté supérieur du cadre de la forme. |
| width | Single | La largeur du cadre de la forme. |
| height | Single | La hauteur du cadre de la forme. |
| createFromTemplate | Boolean | Si vrai, la nouvelle forme sera ajustée à partir du modèle par défaut. Nom non vide, style simple, le texte centré sera associé à la nouvelle forme. Si false alors toutes les valeurs des propriétés de la nouvelle forme auront des valeurs par défaut. |

### Return_Value

Objet AutoShape créé.

### Voir également

* interface [IAutoShape](../../iautoshape)
* enum [ShapeType](../../shapetype)
* interface [IShapeCollection](../../ishapecollection)
* espace de noms [Aspose.Slides](../../ishapecollection)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
