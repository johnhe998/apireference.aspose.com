---
title: ListFormat.ListIndent
second_title: Aspose.Words für .NET-API-Referenz
description: ListFormat methode. Erhöht die Listenebene des aktuellen Absatzes um eine Ebene.
type: docs
weight: 70
url: /de/net/aspose.words.lists/listformat/listindent/
---
## ListFormat.ListIndent method

Erhöht die Listenebene des aktuellen Absatzes um eine Ebene.

```csharp
public void ListIndent()
```

### Bemerkungen

Diese Methode ändert die Listenebene und wendet Formatierungseigenschaften der neuen Ebene an.

In Word-Dokumenten können Listen aus bis zu neun Ebenen bestehen. Listenformatierung für jede Ebene gibt an, welches Aufzählungszeichen oder welche Nummer verwendet wird, linker Einzug, Leerzeichen zwischen dem Aufzählungszeichen und dem Text usw.

### Beispiele

Zeigt, wie Sie Listen mit Aufzählungszeichen und Nummerierungen erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Aspose.Words main advantages are:");

// Eine Liste ermöglicht es uns, Sätze von Absätzen mit Präfixsymbolen und Einzügen zu organisieren und zu dekorieren.
// Wir können verschachtelte Listen erstellen, indem wir die Einrückungsebene erhöhen. 
// Wir können eine Liste beginnen und beenden, indem wir die "ListFormat"-Eigenschaft eines Dokumentenerstellers verwenden. 
// Jeder Absatz, den wir zwischen dem Anfang und dem Ende einer Liste hinzufügen, wird zu einem Element in der Liste.
// Unten sind zwei Arten von Listen, die wir mit einem Document Builder erstellen können.
// 1 - Eine Liste mit Aufzählungszeichen:
// Diese Liste fügt vor jedem Absatz einen Einzug und ein Aufzählungszeichen ("•") ein.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Great performance");
builder.Writeln("High reliability");
builder.Writeln("Quality code and working");
builder.Writeln("Wide variety of features");
builder.Writeln("Easy to understand API");

// Beende die Liste mit Aufzählungszeichen.
builder.ListFormat.RemoveNumbers();

builder.InsertBreak(BreakType.ParagraphBreak);
builder.Writeln("Aspose.Words allows:");

// 2 - Eine nummerierte Liste:
// Nummerierte Listen schaffen eine logische Reihenfolge für ihre Absätze, indem sie jedes Element nummerieren.
builder.ListFormat.ApplyNumberDefault();

// Dieser Absatz ist das erste Element. Das erste Element einer nummerierten Liste hat eine „1“. als sein Listenelementsymbol.
builder.Writeln("Opening documents from different formats:");

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Rufen Sie die Methode "ListIndent" auf, um die aktuelle Listenebene zu erhöhen,
// was eine neue eigenständige Liste mit einem tieferen Einzug am aktuellen Element der ersten Listenebene beginnt.
builder.ListFormat.ListIndent();

Assert.AreEqual(1, builder.ListFormat.ListLevelNumber);

// Dies sind die ersten drei Listenelemente der zweiten Listenebene, die eine Zählung beibehalten
// unabhängig vom Zählerstand der ersten Listenebene. Nach dem aktuellen Listenformat
// Sie haben die Symbole "a.", "b." und "c.".
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");

// Rufen Sie die Methode "ListOutdent" auf, um zur vorherigen Listenebene zurückzukehren.
builder.ListFormat.ListOutdent();

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Diese beiden Absätze setzen die Zählung der ersten Listenebene fort.
// Diese Elemente haben die Symbole "2." und "3."
builder.Writeln("Processing documents");
builder.Writeln("Saving documents in different formats:");

// Wenn wir die Listenebene auf eine Ebene erhöhen, zu der wir zuvor Elemente hinzugefügt haben,
// Die verschachtelte Liste wird von der vorherigen getrennt und ihre Nummerierung beginnt von vorne. 
// Diese Listenelemente haben die Symbole "a.", "b.", "c.", "d." und "e".
builder.ListFormat.ListIndent();
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");
builder.Writeln("MHTML");
builder.Writeln("Plain text");

// Listenebene erneut ausrücken.
builder.ListFormat.ListOutdent();
builder.Writeln("Doing many other things!");

// Ende der nummerierten Liste.
builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.ApplyDefaultBulletsAndNumbers.docx");
```

### Siehe auch

* class [ListFormat](../)
* namensraum [Aspose.Words.Lists](../../listformat/)
* Montage [Aspose.Words](../../../)


