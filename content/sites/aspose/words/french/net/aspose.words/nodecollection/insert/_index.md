---
title: NodeCollection.Insert
second_title: Référence de l'API Aspose.Words pour .NET
description: NodeCollection méthode. Insère un nœud dans la collection à lindex spécifié.
type: docs
weight: 80
url: /fr/net/aspose.words/nodecollection/insert/
---
## NodeCollection.Insert method

Insère un nœud dans la collection à l'index spécifié.

```csharp
public void Insert(int index, Node node)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| index | Int32 | L'index de base zéro du nœud. Les index négatifs sont autorisés et indiquent l'accès depuis le fond de la liste. Par exemple -1 signifie le dernier nœud, -2 signifie l'avant-dernier et ainsi de suite. |
| node | Node | Le nœud à insérer. |

### Exceptions

| exception | condition |
| --- | --- |
| NotSupportedException | La **NodeCollection** est une collection "profonde". |

### Remarques

Le nœud est inséré en tant qu'enfant dans l'objet nœud à partir duquel la collection a été créée.

Si l'index est égal ou supérieur à Count, le nœud est ajouté à la fin de la collection.

Si l'index est négatif et que sa valeur absolue est supérieure à Count, le nœud est ajouté à la fin de la collection.

Si le newChild est déjà dans l'arborescence, il est d'abord supprimé.

Si le nœud inséré a été créé à partir d'un autre document, vous devez utiliser [`ImportNode`](../../documentbase/importnode/) pour importer le nœud dans le document courant. Le nœud importé peut alors être inséré dans le document courant.

### Exemples

Montre comment travailler avec une NodeCollection.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ajoutez du texte au document en insérant Runs using a DocumentBuilder.
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// Chaque invocation de la méthode "Write" crée un nouveau Run,
// qui apparaît ensuite dans la RunCollection du paragraphe parent.
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// Nous pouvons également insérer manuellement un nœud dans la RunCollection.
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// Accédez aux exécutions individuelles et supprimez-les pour supprimer leur texte du document.
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### Voir également

* class [Node](../../node/)
* class [NodeCollection](../)
* espace de noms [Aspose.Words](../../nodecollection/)
* Assemblée [Aspose.Words](../../../)


