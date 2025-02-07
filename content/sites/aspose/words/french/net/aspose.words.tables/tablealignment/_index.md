---
title: Enum TableAlignment
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Tables.TableAlignment énumération. Spécifie lalignement dun tableau en ligne.
type: docs
weight: 6050
url: /fr/net/aspose.words.tables/tablealignment/
---
## TableAlignment enumeration

Spécifie l'alignement d'un tableau en ligne.

```csharp
public enum TableAlignment
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Left | `0` | Le tableau est aligné à gauche. |
| Center | `1` | Le tableau est centré. |
| Right | `2` | Le tableau est aligné à droite. |

### Exemples

Montre comment appliquer une bordure de contour à un tableau.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Aligne le tableau au centre de la page.
table.Alignment = TableAlignment.Center;

// Efface toutes les bordures et tous les ombrages existants du tableau.
table.ClearBorders();
table.ClearShading();

// Ajoute des bordures vertes au contour du tableau.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Remplissez les cellules avec une couleur unie vert clair.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Voir également

* espace de noms [Aspose.Words.Tables](../../aspose.words.tables/)
* Assemblée [Aspose.Words](../../)


