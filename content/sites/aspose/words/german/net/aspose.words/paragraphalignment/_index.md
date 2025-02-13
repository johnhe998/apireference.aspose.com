---
title: Enum ParagraphAlignment
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.ParagraphAlignment opsomming. Gibt die Textausrichtung in einem Absatz an.
type: docs
weight: 4160
url: /de/net/aspose.words/paragraphalignment/
---
## ParagraphAlignment enumeration

Gibt die Textausrichtung in einem Absatz an.

```csharp
public enum ParagraphAlignment
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Left | `0` | Text wird linksbündig ausgerichtet. |
| Center | `1` | Text wird horizontal zentriert. |
| Right | `2` | Text wird rechtsbündig ausgerichtet. |
| Justify | `3` | Text wird links und rechts ausgerichtet. |
| Distributed | `4` | Text wird gleichmäßig verteilt. |
| ArabicMediumKashida | `5` | Nur Arabisch. Die Kashida-Länge für Text wird auf eine vom Verbraucher bestimmte mittlere Länge erweitert. |
| ArabicHighKashida | `7` | Nur Arabisch. Die Kashida-Länge für Text wird auf die größtmögliche Länge erweitert. |
| ArabicLowKashida | `8` | Nur Arabisch. Die Kashida-Länge für Text wird auf eine etwas längere Länge erweitert. |
| ThaiDistributed | `9` | nur Thai. Text wird mit einer Optimierung für Thai ausgerichtet. |
| MathElementCenterAsGroup | `10` | Das einzige mathematische Element in einer Zeile, ausgerichtet als „Zentriert als Gruppe“. |

### Beispiele

Zeigt, wie ein Aspose.Words-Dokument von Hand erstellt wird.

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

// Legen Sie einige Seiteneinrichtungseigenschaften für den Abschnitt fest.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Ein Abschnitt benötigt einen Körper, der seinen gesamten Inhalt enthält und anzeigt
// auf der Seite zwischen Kopf- und Fußzeile des Abschnitts.
Body body = new Body(doc);
section.AppendChild(body);

// Erstellen Sie einen Absatz, legen Sie einige Formatierungseigenschaften fest und hängen Sie ihn dann als untergeordnetes Element an den Textkörper an.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Fügen Sie schließlich etwas Inhalt hinzu, um das Dokument zu erstellen. Erstellen Sie einen Lauf,
// Aussehen und Inhalt festlegen und dann als untergeordnetes Element an den Absatz anhängen.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


