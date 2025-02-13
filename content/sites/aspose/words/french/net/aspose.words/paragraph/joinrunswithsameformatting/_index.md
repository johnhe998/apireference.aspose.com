---
title: Paragraph.JoinRunsWithSameFormatting
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph méthode. Les jointures sexécutent avec le même formatage dans le paragraphe.
type: docs
weight: 280
url: /fr/net/aspose.words/paragraph/joinrunswithsameformatting/
---
## Paragraph.JoinRunsWithSameFormatting method

Les jointures s'exécutent avec le même formatage dans le paragraphe.

```csharp
public int JoinRunsWithSameFormatting()
```

### Return_Value

Nombre de jointures effectuées. Lorsque **N** les pistes adjacentes sont jointes, elles comptent comme **N-1** rejoint.

### Exemples

Montre comment simplifier des paragraphes en fusionnant des séquences superflues.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère quatre passages de texte dans le paragraphe.
builder.Write("Run 1. ");
builder.Write("Run 2. ");
builder.Write("Run 3. ");
builder.Write("Run 4. ");

// Si nous ouvrons ce document dans Microsoft Word, le paragraphe ressemblera à un corps de texte homogène.
// Cependant, il consistera en quatre exécutions distinctes avec le même formatage. Des paragraphes fragmentés comme celui-ci
// peut se produire lorsque nous modifions manuellement plusieurs fois des parties d'un paragraphe dans Microsoft Word.
Paragraph para = builder.CurrentParagraph;

Assert.AreEqual(4, para.Runs.Count);

// Modifie le style de la dernière exécution pour la distinguer des trois premières.
para.Runs[3].Font.StyleIdentifier = StyleIdentifier.Emphasis;

// On peut lancer la méthode "JoinRunsWithSameFormatting" pour optimiser le contenu du document
// en fusionnant des exécutions similaires en une seule, réduisant ainsi leur nombre global.
// Cette méthode renvoie également le nombre d'exécutions que cette méthode a fusionnées.
// Ces deux fusions se sont produites pour combiner les exécutions #1, #2 et #3,
// tout en omettant Run #4 car il a un style incompatible.
Assert.AreEqual(2, para.JoinRunsWithSameFormatting());

// Le nombre d'exécutions restantes sera égal au nombre d'origine
// moins le nombre de run merges que la méthode "JoinRunsWithSameFormatting" a effectué.
Assert.AreEqual(2, para.Runs.Count);
Assert.AreEqual("Run 1. Run 2. Run 3. ", para.Runs[0].Text);
Assert.AreEqual("Run 4. ", para.Runs[1].Text);
```

### Voir également

* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


