---
title: CompositeNode.Count
second_title: Aspose.Words für .NET-API-Referenz
description: CompositeNode eigendom. Ruft die Anzahl der unmittelbaren Kinder dieses Knotens ab.
type: docs
weight: 20
url: /de/net/aspose.words/compositenode/count/
---
## CompositeNode.Count property

Ruft die Anzahl der unmittelbaren Kinder dieses Knotens ab.

```csharp
public int Count { get; }
```

### Beispiele

Zeigt, wie untergeordnete Knoten in der Sammlung untergeordneter Elemente eines CompositeNode hinzugefügt, aktualisiert und gelöscht werden.

```csharp
Document doc = new Document();

// Ein leeres Dokument hat standardmäßig einen Absatz.
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// Zusammengesetzte Knoten wie unser Absatz können andere zusammengesetzte und Inline-Knoten als Kinder enthalten.
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Run paragraphText = new Run(doc, "Initial text. ");
paragraph.AppendChild(paragraphText);

// Drei weitere Ausführungsknoten erstellen.
Run run1 = new Run(doc, "Run 1. ");
Run run2 = new Run(doc, "Run 2. ");
Run run3 = new Run(doc, "Run 3. ");

// Der Dokumentkörper zeigt diese Läufe erst an, wenn wir sie in einen zusammengesetzten Knoten einfügen
// das selbst ein Teil des Knotenbaums des Dokuments ist, wie wir es beim ersten Durchlauf getan haben.
// Wir können bestimmen, wo sich der Textinhalt von Knoten befindet, die wir einfügen
// wird im Dokument angezeigt, indem eine Einfügeposition relativ zu einem anderen Knoten im Absatz angegeben wird.
Assert.AreEqual("Initial text.", paragraph.GetText().Trim());

// Füge den zweiten Lauf in den Absatz vor dem ersten Lauf ein.
paragraph.InsertBefore(run2, paragraphText);

Assert.AreEqual("Run 2. Initial text.", paragraph.GetText().Trim());

// Füge den dritten Lauf nach dem ersten Lauf ein.
paragraph.InsertAfter(run3, paragraphText);

Assert.AreEqual("Run 2. Initial text. Run 3.", paragraph.GetText().Trim());

// Den ersten Lauf am Anfang der Sammlung untergeordneter Knoten des Absatzes einfügen.
paragraph.PrependChild(run1);

Assert.AreEqual("Run 1. Run 2. Initial text. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(4, paragraph.GetChildNodes(NodeType.Any, true).Count);

// Wir können den Inhalt des Laufs ändern, indem wir vorhandene untergeordnete Knoten bearbeiten und löschen.
((Run)paragraph.GetChildNodes(NodeType.Run, true)[1]).Text = "Updated run 2. ";
paragraph.GetChildNodes(NodeType.Run, true).Remove(paragraphText);

Assert.AreEqual("Run 1. Updated run 2. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(3, paragraph.GetChildNodes(NodeType.Any, true).Count);
```

### Siehe auch

* class [CompositeNode](../)
* namensraum [Aspose.Words](../../compositenode/)
* Montage [Aspose.Words](../../../)


