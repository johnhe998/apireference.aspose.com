---
title: Enum PreferredWidthType
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Tables.PreferredWidthType énumération. Spécifie lunité de mesure pour la largeur préférée dun tableau ou dune cellule.
type: docs
weight: 6000
url: /fr/net/aspose.words.tables/preferredwidthtype/
---
## PreferredWidthType enumeration

Spécifie l'unité de mesure pour la largeur préférée d'un tableau ou d'une cellule.

```csharp
public enum PreferredWidthType
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Auto | `1` | La largeur préférée n'est pas spécifiée. La largeur réelle du tableau ou de la cellule est soit spécifiée à l'aide de la largeur explicite, soit sera déterminée automatiquement par l'algorithme de mise en page du tableau lors de l'affichage du tableau, en fonction du paramètre d'ajustement automatique du tableau. |
| Percent | `2` | Mesurez la largeur de l'élément actuel à l'aide d'un pourcentage spécifié. |
| Points | `3` | Mesurez la largeur de l'élément actuel à l'aide d'un nombre de points spécifié (1/72 pouce). |

### Exemples

Montre comment vérifier le type de largeur préféré et la valeur d'une cellule de tableau.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

Assert.AreEqual(PreferredWidthType.Percent, firstCell.CellFormat.PreferredWidth.Type);
Assert.AreEqual(11.16d, firstCell.CellFormat.PreferredWidth.Value);
```

### Voir également

* class [PreferredWidth](../preferredwidth/)
* espace de noms [Aspose.Words.Tables](../../aspose.words.tables/)
* Assemblée [Aspose.Words](../../)


