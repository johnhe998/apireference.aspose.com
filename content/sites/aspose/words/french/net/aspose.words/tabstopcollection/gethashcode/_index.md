---
title: TabStopCollection.GetHashCode
second_title: Référence de l'API Aspose.Words pour .NET
description: TabStopCollection méthode. Sert de fonction de hachage pour ce type.
type: docs
weight: 80
url: /fr/net/aspose.words/tabstopcollection/gethashcode/
---
## TabStopCollection.GetHashCode method

Sert de fonction de hachage pour ce type.

```csharp
public override int GetHashCode()
```

### Exemples

Montre comment utiliser la collection de taquets de tabulation d'un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 points correspond à un "pouce" sur la règle de taquet de Microsoft Word.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// Chaque caractère "tab" amène le curseur du générateur à l'emplacement du prochain taquet de tabulation.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// Chaque paragraphe obtient sa collection de taquets de tabulation, qui clone ses valeurs à partir de la collection de taquets de tabulation du générateur de document.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// Une collection d'arrêts de tabulation peut nous diriger vers TabStops avant et après certaines positions.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// Nous pouvons effacer la collection de taquets de tabulation d'un paragraphe pour revenir au comportement de tabulation par défaut.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### Voir également

* class [TabStopCollection](../)
* espace de noms [Aspose.Words](../../tabstopcollection/)
* Assemblée [Aspose.Words](../../../)


