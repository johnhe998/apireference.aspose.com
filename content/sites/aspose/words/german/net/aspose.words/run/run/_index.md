---
title: Run.Run
second_title: Aspose.Words für .NET-API-Referenz
description: Run constructeur. Initialisiert eine neue Instanz von Laufen Klasse.
type: docs
weight: 10
url: /de/net/aspose.words/run/run/
---
## Run(DocumentBase) {#constructor}

Initialisiert eine neue Instanz von **Laufen** Klasse.

```csharp
public Run(DocumentBase doc)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| doc | DocumentBase | Das Besitzerdokument. |

### Bemerkungen

Wann **Laufen** erstellt wird, gehört es zum angegebenen Dokument, ist aber noch nicht Teil des Dokuments und **Elternknoten** ist Null.

Anhängen **Laufen** zum Dokument verwenden Sie InsertAfter oder InsertBefore für den Absatz, an dem Sie den Lauf einfügen möchten.

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

* class [DocumentBase](../../documentbase/)
* class [Run](../)
* namensraum [Aspose.Words](../../run/)
* Montage [Aspose.Words](../../../)

---

## Run(DocumentBase, string) {#constructor_1}

Initialisiert eine neue Instanz von **Laufen** Klasse.

```csharp
public Run(DocumentBase doc, string text)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| doc | DocumentBase | Das Besitzerdokument. |
| text | String | Der Lauftext. |

### Bemerkungen

Wann **Laufen** erstellt wird, gehört es zum angegebenen Dokument, ist aber noch nicht Teil des Dokuments und **Elternknoten** ist Null.

Anhängen **Laufen** zum Dokument verwenden Sie InsertAfter oder InsertBefore für den Absatz, an dem Sie den Lauf einfügen möchten.

### Beispiele

Zeigt, wie ein Textverlauf mithilfe seiner Eigenschaft font formatiert wird.

```csharp
Document doc = new Document();
Run run = new Run(doc, "Hello world!");

Aspose.Words.Font font = run.Font;
font.Name = "Courier New";
font.Size = 36;
font.HighlightColor = Color.Yellow;

doc.FirstSection.Body.FirstParagraph.AppendChild(run);
doc.Save(ArtifactsDir + "Font.CreateFormattedRun.docx");
```

### Siehe auch

* class [DocumentBase](../../documentbase/)
* class [Run](../)
* namensraum [Aspose.Words](../../run/)
* Montage [Aspose.Words](../../../)


