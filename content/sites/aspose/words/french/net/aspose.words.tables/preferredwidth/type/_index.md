---
title: PreferredWidth.Type
second_title: Référence de l'API Aspose.Words pour .NET
description: PreferredWidth propriété. Obtient lunité de mesure utilisée pour cette valeur de largeur préférée.
type: docs
weight: 40
url: /fr/net/aspose.words.tables/preferredwidth/type/
---
## PreferredWidth.Type property

Obtient l'unité de mesure utilisée pour cette valeur de largeur préférée.

```csharp
public PreferredWidthType Type { get; }
```

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

* enum [PreferredWidthType](../../preferredwidthtype/)
* class [PreferredWidth](../)
* espace de noms [Aspose.Words.Tables](../../preferredwidth/)
* Assemblée [Aspose.Words](../../../)


