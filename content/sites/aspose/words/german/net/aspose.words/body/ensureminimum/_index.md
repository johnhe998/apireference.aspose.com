---
title: Body.EnsureMinimum
second_title: Aspose.Words für .NET-API-Referenz
description: Body methode. Wenn das letzte untergeordnete Element kein Absatz ist wird ein leerer Absatz erstellt und angehängt.
type: docs
weight: 50
url: /de/net/aspose.words/body/ensureminimum/
---
## Body.EnsureMinimum method

Wenn das letzte untergeordnete Element kein Absatz ist, wird ein leerer Absatz erstellt und angehängt.

```csharp
public void EnsureMinimum()
```

### Beispiele

Löscht den Haupttext aus allen Abschnitten des Dokuments und belässt die Abschnitte selbst.

```csharp
Document doc = new Document();

// Ein leeres Dokument enthält einen Abschnitt, einen Hauptteil und einen Absatz.
// Rufen Sie die Methode "RemoveAllChildren" auf, um alle diese Knoten zu entfernen,
// und am Ende einen Dokumentknoten ohne Kinder haben.
doc.RemoveAllChildren();

// Dieses Dokument hat jetzt keine zusammengesetzten untergeordneten Knoten, denen wir Inhalte hinzufügen können.
// Wenn wir es bearbeiten möchten, müssen wir seine Knotensammlung neu füllen.
// Erstellen Sie zuerst einen neuen Abschnitt und hängen Sie ihn dann als untergeordnetes Element an den Stammdokumentknoten an.
Section section = new Section(doc);
doc.AppendChild(section);

// Ein Abschnitt benötigt einen Körper, der seinen gesamten Inhalt enthält und anzeigt
// auf der Seite zwischen Kopf- und Fußzeile des Abschnitts.
Body body = new Body(doc);
section.AppendChild(body);

// Dieser Körper hat keine Kinder, daher können wir ihm noch keine Läufe hinzufügen.
Assert.AreEqual(0, doc.FirstSection.Body.GetChildNodes(NodeType.Any, true).Count);

// Rufen Sie "EnsureMinimum" auf, um sicherzustellen, dass dieser Hauptteil mindestens einen leeren Absatz enthält. 
body.EnsureMinimum();

// Jetzt können wir Läufe zum Hauptteil hinzufügen und das Dokument dazu bringen, sie anzuzeigen.
body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Siehe auch

* class [Body](../)
* namensraum [Aspose.Words](../../body/)
* Montage [Aspose.Words](../../../)


