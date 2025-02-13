---
title: NodeList.Item
second_title: Aspose.Words für .NET-API-Referenz
description: NodeList eigendom. Ruft einen Knoten am angegebenen Index ab.
type: docs
weight: 20
url: /de/net/aspose.words/nodelist/item/
---
## NodeList indexer

Ruft einen Knoten am angegebenen Index ab.

```csharp
public Node this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Ein Index in die Liste der Knoten. |

### Bemerkungen

Der Index ist nullbasiert.

Negative Indizes sind zulässig und zeigen den Zugriff von der Rückseite der Sammlung an. Zum Beispiel bedeutet -1 das letzte Element, -2 bedeutet das vorletzte und so weiter.

Wenn der Index größer oder gleich der Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

Wenn der Index negativ ist und sein absoluter Wert größer als die Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

### Beispiele

Zeigt die Verwendung von XPaths zum Navigieren in einer NodeList.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einige Knoten mit einem DocumentBuilder einfügen.
builder.Writeln("Hello world!");

builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();

#if NET48 || JAVA
builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
#elif NET5_0_OR_GREATER || __MOBILE__
using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
    builder.InsertImage(image);
#endif

// Unser Dokument enthält drei Run-Knoten.
NodeList nodeList = doc.SelectNodes("//Laufen");

Assert.AreEqual(3, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Hello world!"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Verwenden Sie einen doppelten Schrägstrich, um alle Run-Knoten auszuwählen
// die indirekte Nachkommen eines Tabellenknotens sind, was die Läufe innerhalb der beiden von uns eingefügten Zellen wären.
nodeList = doc.SelectNodes("//Table//Laufen");

Assert.AreEqual(2, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Einfache Schrägstriche geben direkte Nachkommenbeziehungen an,
// die wir übersprungen haben, als wir doppelte Schrägstriche verwendet haben.
Assert.AreEqual(doc.SelectNodes(" //Tabelle//Run"),
    doc.SelectNodes("//Tabelle/Zeile/Zelle/Absatz/Lauf"));

// Auf die Form zugreifen, die das eingefügte Bild enthält.
nodeList = doc.SelectNodes("//Form");

Assert.AreEqual(1, nodeList.Count);

Shape shape = (Shape)nodeList[0];
Assert.True(shape.HasImage);
```

### Siehe auch

* class [Node](../../node/)
* class [NodeList](../)
* namensraum [Aspose.Words](../../nodelist/)
* Montage [Aspose.Words](../../../)


