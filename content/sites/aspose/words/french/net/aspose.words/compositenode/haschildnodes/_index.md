---
title: CompositeNode.HasChildNodes
second_title: Référence de l'API Aspose.Words pour .NET
description: CompositeNode propriété. Renvoie vrai si ce nœud a des nœuds enfants.
type: docs
weight: 40
url: /fr/net/aspose.words/compositenode/haschildnodes/
---
## CompositeNode.HasChildNodes property

Renvoie vrai si ce nœud a des nœuds enfants.

```csharp
public bool HasChildNodes { get; }
```

### Exemples

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

* class [CompositeNode](../)
* espace de noms [Aspose.Words](../../compositenode/)
* Assemblée [Aspose.Words](../../../)


