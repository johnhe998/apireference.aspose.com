---
title: LayoutCollector.GetEntity
second_title: Aspose.Words für .NET-API-Referenz
description: LayoutCollector methode. Gibt eine undurchsichtige Position von zurückLayoutEnumerator was dem angegebenen Knoten entspricht. Sie können den zurückgegebenen Wert als Argument für verwendenCurrent Da das Dokument das aufgezählt wird und das Dokument des Knotens identisch sind.
type: docs
weight: 50
url: /de/net/aspose.words.layout/layoutcollector/getentity/
---
## LayoutCollector.GetEntity method

Gibt eine undurchsichtige Position von zurück[`LayoutEnumerator`](../../layoutenumerator/) was dem angegebenen Knoten entspricht. Sie können den zurückgegebenen Wert als Argument für verwenden[`Current`](../../layoutenumerator/current/) Da das Dokument, das aufgezählt wird, und das Dokument des Knotens identisch sind.

```csharp
public object GetEntity(Node node)
```

### Bemerkungen

Diese Methode funktioniert nur für[`Paragraph`](../../../aspose.words/paragraph/) Knoten sowie unteilbare Inline-Knoten, zB[`BookmarkStart`](../../../aspose.words/bookmarkstart/) oder[`Shape`](../../../aspose.words.drawing/shape/) Es funktioniert nicht für[`Run`](../../../aspose.words/run/) ,[`Cell`](../../../aspose.words.tables/cell/)[`Row`](../../../aspose.words.tables/row/) oder[`Table`](../../../aspose.words.tables/table/) Knoten und Knoten innerhalb der Kopf-/Fußzeile.

Beachten Sie, dass die für a zurückgegebene Entität[`Paragraph`](../../../aspose.words/paragraph/) node ist eine Absatzumbruchspanne. Verwenden Sie die geeignete Methode, um zur übergeordneten Linie aufzusteigen

Wenn Sie zu a navigieren müssen[`Run`](../../../aspose.words/run/) von Text, dann können Sie ein Lesezeichen direkt vor it einfügen und dann stattdessen zum Lesezeichen navigieren.

Wenn Sie zu a navigieren müssen[`Cell`](../../../aspose.words.tables/cell/) Knoten, dann können Sie zu a wechseln[`Paragraph`](../../../aspose.words/paragraph/) Knoten in dieser Zelle und steige dann zu einer übergeordneten Entität auf. Der gleiche Ansatz kann für verwendet werden[`Row`](../../../aspose.words.tables/row/) und[`Table`](../../../aspose.words.tables/table/) Knoten.

### Beispiele

Zeigt, wie die Seitenbereiche angezeigt werden, die ein Knoten umfasst.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// Rufen Sie die Methode "GetNumPagesSpanned" auf, um zu zählen, wie viele Seiten der Inhalt unseres Dokuments umfasst.
// Da das Dokument leer ist, ist diese Seitenzahl derzeit null.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// Das Dokument mit 5 Seiten Inhalt füllen.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// Vor dem Layout-Sammler müssen wir die Methode "UpdatePageLayout" aufrufen, um uns zu geben
// eine genaue Zahl für alle Layout-bezogenen Metriken, wie z. B. die Seitenzahl.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// Wir können die Nummern der Start- und Endseiten jedes Knotens und ihre gesamten Seitenspannen sehen.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// Wir können mit einem LayoutEnumerator über die Layout-Entitäten iterieren.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// Der LayoutEnumerator kann die Sammlung von Layout-Entitäten wie einen Baum durchlaufen.
// Wir können es auch auf die entsprechende Layout-Entität eines beliebigen Knotens anwenden.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### Siehe auch

* class [Node](../../../aspose.words/node/)
* class [LayoutCollector](../)
* namensraum [Aspose.Words.Layout](../../layoutcollector/)
* Montage [Aspose.Words](../../../)


