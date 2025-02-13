---
title: TabStopCollection.GetIndexByPosition
second_title: Aspose.Words für .NET-API-Referenz
description: TabStopCollection methode. Ruft den Index eines Tabstopps mit der angegebenen Position in Punkten ab.
type: docs
weight: 90
url: /de/net/aspose.words/tabstopcollection/getindexbyposition/
---
## TabStopCollection.GetIndexByPosition method

Ruft den Index eines Tabstopps mit der angegebenen Position in Punkten ab.

```csharp
public int GetIndexByPosition(double position)
```

### Beispiele

Zeigt, wie Sie nach einer Position suchen, um festzustellen, ob dort ein Tabstopp vorhanden ist, und wie Sie seinen Index abrufen.

```csharp
Document doc = new Document();
TabStopCollection tabStops = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.TabStops;

// Füge einen Tabstopp an einer Position von 30 mm hinzu.
tabStops.Add(ConvertUtil.MillimeterToPoint(30), TabAlignment.Left, TabLeader.Dashes);

// Ein Ergebnis von "0", das von "GetIndexByPosition" zurückgegeben wird, bestätigt, dass ein Tabstopp ist
// bei 30 mm existiert in dieser Sammlung und ist bei Index 0.
Assert.AreEqual(0, tabStops.GetIndexByPosition(ConvertUtil.MillimeterToPoint(30)));

// Eine von "GetIndexByPosition" zurückgegebene "-1" bestätigt dies
// In dieser Sammlung gibt es keinen Tabstopp mit einer Position von 60 mm.
Assert.AreEqual(-1, tabStops.GetIndexByPosition(ConvertUtil.MillimeterToPoint(60)));
```

### Siehe auch

* class [TabStopCollection](../)
* namensraum [Aspose.Words](../../tabstopcollection/)
* Montage [Aspose.Words](../../../)


