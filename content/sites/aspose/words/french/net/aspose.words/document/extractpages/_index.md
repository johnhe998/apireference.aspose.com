---
title: Document.ExtractPages
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Renvoie leDocument objet représentant une plage de pages spécifiée.
type: docs
weight: 580
url: /fr/net/aspose.words/document/extractpages/
---
## Document.ExtractPages method

Renvoie le[`Document`](../) objet représentant une plage de pages spécifiée.

```csharp
public Document ExtractPages(int index, int count)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| index | Int32 | Index de base zéro de la première page à extraire. |
| count | Int32 | Nombre de pages à extraire. |

### Remarques

Le document résultant devrait ressembler à celui de MS Word, comme si nous avions effectué "Imprimer des pages spécifiques" - la numérotation, les en-têtes/pieds de page et la disposition des tableaux croisés seront conservés. Mais en raison d'un grand nombre de nuances, apparaissant tout en réduisant le nombre de pages, la correspondance complète de la mise en page est une tâche compliquée et silencieuse nécessitant beaucoup d'efforts. En fonction de la complexité du document, il peut y avoir de légères différences dans la mise en page du contenu du document résultant par rapport au document source. Tout commentaire serait être grandement apprécié.

### Exemples

Montre comment obtenir une plage de pages spécifiée à partir du document.

```csharp
Document doc = new Document(MyDir + "Layout entities.docx");

doc = doc.ExtractPages(0, 2);

doc.Save(ArtifactsDir + "Document.ExtractPages.docx");
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


