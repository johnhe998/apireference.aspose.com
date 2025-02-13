---
title: Node.PreviousSibling
second_title: Référence de l'API Aspose.Words pour .NET
description: Node propriété. Obtient le nœud précédant immédiatement ce nœud.
type: docs
weight: 70
url: /fr/net/aspose.words/node/previoussibling/
---
## Node.PreviousSibling property

Obtient le nœud précédant immédiatement ce nœud.

```csharp
public Node PreviousSibling { get; }
```

### Remarques

S'il n'y a pas de nœud précédent, une valeur nulle est renvoyée.

### Exemples

Montre comment utiliser les méthodes de Node et CompositeNode pour supprimer une section avant la dernière section du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Les deux sections sont frères l'une de l'autre.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Supprime une section en fonction de sa relation de fratrie avec une autre section.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// La section que nous avons supprimée était la première, laissant le document avec seulement la seconde.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Voir également

* class [Node](../)
* espace de noms [Aspose.Words](../../node/)
* Assemblée [Aspose.Words](../../../)


