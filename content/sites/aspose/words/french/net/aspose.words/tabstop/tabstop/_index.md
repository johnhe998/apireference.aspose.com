---
title: TabStop.TabStop
second_title: Référence de l'API Aspose.Words pour .NET
description: TabStop constructeur. Initialise une nouvelle instance de cette classe.
type: docs
weight: 10
url: /fr/net/aspose.words/tabstop/tabstop/
---
## TabStop(double) {#constructor}

Initialise une nouvelle instance de cette classe.

```csharp
public TabStop(double position)
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

* class [TabStop](../)
* espace de noms [Aspose.Words](../../tabstop/)
* Assemblée [Aspose.Words](../../../)

---

## TabStop(double, TabAlignment, TabLeader) {#constructor_1}

Initialise une nouvelle instance de cette classe.

```csharp
public TabStop(double position, TabAlignment alignment, TabLeader leader)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| position | Double | La position du taquet de tabulation en points. |
| alignment | TabAlignment | UN[`TabAlignment`](../../tabalignment/) la valeur that spécifie l'alignement du texte à ce taquet de tabulation. |
| leader | TabLeader | UN[`TabLeader`](../../tableader/) valeur qui spécifie le type de la ligne de repère affichée sous le caractère de tabulation. |

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

* enum [TabAlignment](../../tabalignment/)
* enum [TabLeader](../../tableader/)
* class [TabStop](../)
* espace de noms [Aspose.Words](../../tabstop/)
* Assemblée [Aspose.Words](../../../)


