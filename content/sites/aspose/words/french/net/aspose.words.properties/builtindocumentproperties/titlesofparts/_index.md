---
title: BuiltInDocumentProperties.TitlesOfParts
second_title: Référence de l'API Aspose.Words pour .NET
description: BuiltInDocumentProperties propriété. Chaque chaîne du tableau spécifie le nom dune partie dans le document.
type: docs
weight: 300
url: /fr/net/aspose.words.properties/builtindocumentproperties/titlesofparts/
---
## BuiltInDocumentProperties.TitlesOfParts property

Chaque chaîne du tableau spécifie le nom d'une partie dans le document.

```csharp
public string[] TitlesOfParts { get; set; }
```

### Remarques

Aspose.Words ne met pas à jour cette propriété.

### Exemples

Affiche la relation entre les propriétés "HeadingPairs" et "TitlesOfParts".

```csharp
Document doc = new Document(MyDir + "Heading pairs and titles of parts.docx");

// Nous pouvons trouver les valeurs combinées de ces collections via
// "Fichier" -> "Propriétés" -> "Propriétés avancées" -> Onglet "Contenu".
// La propriété HeadingPairs est une collection de <string, int> paires qui
// détermine le nombre de parties de document sur lesquelles un titre s'étend.
object[] headingPairs = doc.BuiltInDocumentProperties.HeadingPairs;

// La propriété TitlesOfParts contient les noms des parties qui appartiennent aux en-têtes ci-dessus.
string[] titlesOfParts = doc.BuiltInDocumentProperties.TitlesOfParts;

int headingPairsIndex = 0;
int titlesOfPartsIndex = 0;
while (headingPairsIndex < headingPairs.Length)
{
    Console.WriteLine($"Parts for {headingPairs[headingPairsIndex++]}:");
    int partsCount = Convert.ToInt32(headingPairs[headingPairsIndex++]);

    for (int i = 0; i < partsCount; i++)
        Console.WriteLine($"\t\"{titlesOfParts[titlesOfPartsIndex++]}\"");
}
```

### Voir également

* class [BuiltInDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../builtindocumentproperties/)
* Assemblée [Aspose.Words](../../../)


