---
title: TabStopCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: TabStopCollection eigendom. Ruft einen Tabstopp am angegebenen Index ab.
type: docs
weight: 20
url: /de/net/aspose.words/tabstopcollection/item/
---
## TabStopCollection indexer (1 of 2)

Ruft einen Tabstopp am angegebenen Index ab.

```csharp
public TabStop this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Ein Index in die Sammlung von Tabstopps. |

### Beispiele

Zeigt, wie Sie mit der Sammlung von Tabstopps eines Dokuments arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 Punkte sind ein "Zoll" auf dem Microsoft Word-Tabulatorlineal.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// Jedes "Tab"-Zeichen bringt den Cursor des Builders an die Position des nächsten Tabstopps.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// Jeder Absatz erhält seine Tabstopp-Sammlung, die seine Werte aus der Tabstopp-Sammlung des Dokumentenerstellers klont.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// Eine Tabstop-Sammlung kann uns auf TabStops vor und nach bestimmten Positionen verweisen.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// Wir können die Tabstopp-Sammlung eines Absatzes löschen, um zum Standard-Tab-Verhalten zurückzukehren.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### Siehe auch

* class [TabStop](../../tabstop/)
* class [TabStopCollection](../)
* namensraum [Aspose.Words](../../tabstopcollection/)
* Montage [Aspose.Words](../../../)

---

## TabStopCollection indexer (2 of 2)

Ruft einen Tabstopp an der angegebenen Position ab.

```csharp
public TabStop this[double position] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| position | Die Position (in Punkt) des Tabstopps. |

### Bemerkungen

Gibt null zurück, wenn an der angegebenen Position kein Tabstopp gefunden wird.

### Beispiele

Zeigt, wie Sie mit der Sammlung von Tabstopps eines Dokuments arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 Punkte sind ein "Zoll" auf dem Microsoft Word-Tabulatorlineal.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// Jedes "Tab"-Zeichen bringt den Cursor des Builders an die Position des nächsten Tabstopps.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// Jeder Absatz erhält seine Tabstopp-Sammlung, die seine Werte aus der Tabstopp-Sammlung des Dokumentenerstellers klont.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// Eine Tabstop-Sammlung kann uns auf TabStops vor und nach bestimmten Positionen verweisen.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// Wir können die Tabstopp-Sammlung eines Absatzes löschen, um zum Standard-Tab-Verhalten zurückzukehren.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### Siehe auch

* class [TabStop](../../tabstop/)
* class [TabStopCollection](../)
* namensraum [Aspose.Words](../../tabstopcollection/)
* Montage [Aspose.Words](../../../)


