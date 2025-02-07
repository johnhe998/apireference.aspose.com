---
title: FontInfoCollection.Contains
second_title: Aspose.Words für .NET-API-Referenz
description: FontInfoCollection methode. Bestimmt ob die Sammlung eine Schriftart mit dem angegebenen Namen enthält.
type: docs
weight: 60
url: /de/net/aspose.words.fonts/fontinfocollection/contains/
---
## FontInfoCollection.Contains method

Bestimmt, ob die Sammlung eine Schriftart mit dem angegebenen Namen enthält.

```csharp
public bool Contains(string name)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| name | String | Name der Schriftart, die gesucht werden soll, ohne Berücksichtigung der Groß-/Kleinschreibung. |

### Rückgabewert

True, wenn das Element in der Sammlung gefunden wird; andernfalls falsch.

### Beispiele

Zeigt Informationen zu den Schriftarten an, die im leeren Dokument vorhanden sind.

```csharp
Document doc = new Document();

// Ein leeres Dokument enthält 3 Standardschriften. Jede Schriftart im Dokument
// wird ein entsprechendes FontInfo-Objekt haben, das Details zu dieser Schriftart enthält.
Assert.AreEqual(3, doc.FontInfos.Count);

Assert.True(doc.FontInfos.Contains("Times New Roman"));
Assert.AreEqual(204, doc.FontInfos["Times New Roman"].Charset);

Assert.True(doc.FontInfos.Contains("Symbol"));
Assert.True(doc.FontInfos.Contains("Arial"));
```

### Siehe auch

* class [FontInfoCollection](../)
* namensraum [Aspose.Words.Fonts](../../fontinfocollection/)
* Montage [Aspose.Words](../../../)


