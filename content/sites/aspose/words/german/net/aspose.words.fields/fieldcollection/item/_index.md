---
title: FieldCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: FieldCollection eigendom. Gibt ein Feld am angegebenen Index zurück.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldcollection/item/
---
## FieldCollection indexer

Gibt ein Feld am angegebenen Index zurück.

```csharp
public Field this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Ein Index in die Sammlung. |

### Bemerkungen

Der Index ist nullbasiert.

Negative Indizes sind zulässig und zeigen den Zugriff von der Rückseite der Sammlung an. Zum Beispiel bedeutet -1 das letzte Element, -2 bedeutet das vorletzte und so weiter.

Wenn der Index größer oder gleich der Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

Wenn der Index negativ ist und sein absoluter Wert größer als die Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

### Beispiele

Zeigt, wie Felder aus einer Feldsammlung entfernt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
builder.InsertField(" TIME ");
builder.InsertField(" REVNUM ");
builder.InsertField(" AUTHOR  \"John Doe\" ");
builder.InsertField(" SUBJECT \"My Subject\" ");
builder.InsertField(" QUOTE \"Hello world!\" ");
doc.UpdateFields();

FieldCollection fields = doc.Range.Fields;

Assert.AreEqual(6, fields.Count);

// Im Folgenden finden Sie vier Möglichkeiten zum Entfernen von Feldern aus einer Feldsammlung.
// 1 - Holen Sie sich ein Feld, um sich selbst zu entfernen:
fields[0].Remove();
Assert.AreEqual(5, fields.Count);

// 2 - Holen Sie sich die Sammlung, um ein Feld zu entfernen, das wir an seine Entfernungsmethode übergeben:
Field lastField = fields[3];
fields.Remove(lastField);
Assert.AreEqual(4, fields.Count);

// 3 - Entfernen Sie ein Feld aus einer Sammlung an einem Index:
fields.RemoveAt(2);
Assert.AreEqual(3, fields.Count);

// 4 - Alle Felder auf einmal aus der Sammlung entfernen:
fields.Clear();
Assert.AreEqual(0, fields.Count);
```

### Siehe auch

* class [Field](../../field/)
* class [FieldCollection](../)
* namensraum [Aspose.Words.Fields](../../fieldcollection/)
* Montage [Aspose.Words](../../../)


