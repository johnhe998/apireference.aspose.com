---
title: Table.FirstRow
second_title: Référence de l'API Aspose.Words pour .NET
description: Table propriété. Renvoie le premier Ligne nœud dans la table.
type: docs
weight: 160
url: /fr/net/aspose.words.tables/table/firstrow/
---
## Table.FirstRow property

Renvoie le premier **Ligne** nœud dans la table.

```csharp
public Row FirstRow { get; }
```

### Exemples

Montre comment supprimer les première et dernière lignes de tous les tableaux d'un document.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

Montre comment combiner les lignes de deux tables en une seule.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Vous trouverez ci-dessous deux manières d'obtenir un tableau à partir d'un document.
// 1 - Depuis la collection "Tables" d'un noeud Body :
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - Utilisation de la méthode "GetChild" :
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Ajoute toutes les lignes de la table actuelle à la suivante.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Supprime le conteneur de table vide.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Voir également

* class [Row](../../row/)
* class [Table](../)
* espace de noms [Aspose.Words.Tables](../../table/)
* Assemblée [Aspose.Words](../../../)


