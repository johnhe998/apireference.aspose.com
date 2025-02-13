---
title: DocumentBuilder.InsertTableOfContents
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Fügt ein TOCFeld Inhaltsverzeichnis in das Dokument ein.
type: docs
weight: 440
url: /de/net/aspose.words/documentbuilder/inserttableofcontents/
---
## DocumentBuilder.InsertTableOfContents method

Fügt ein TOC-Feld (Inhaltsverzeichnis) in das Dokument ein.

```csharp
public Field InsertTableOfContents(string switches)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| switches | String | Das TOC-Feld wechselt. |

### Bemerkungen

Diese Methode fügt ein TOC-Feld (Inhaltsverzeichnis) an der aktuellen Position in das Dokument ein.

Ein Inhaltsverzeichnis in einem Word-Dokument kann auf verschiedene Arten erstellt und mit einer Vielzahl von Optionen formatiert werden. Die Art und Weise, wie die Tabelle aufgebaut und von Microsoft Word angezeigt wird, wird durch die Feldschalter gesteuert.

Der einfachste Weg, die Schalter anzugeben, besteht darin, eine Tabelle mit Inhalten in ein Word-Dokument einzufügen und zu konfigurieren, indem Sie das Menü Einfügen-&gt;Referenz-&gt;Index und Tabellen verwenden, und dann die Anzeige der Feldcodes einschalten, um die Schalter zu sehen. Sie können Alt+F9 in Microsoft Word drücken, um die Anzeige von Feldcodes ein- oder auszuschalten.

Nach dem Erstellen eines Inhaltsverzeichnisses wird beispielsweise das folgende Feld in das Dokument eingefügt : **{ Inhaltsverzeichnis \o "1-3" \h \z \u }** . Sie können kopieren **\o "1-3" \h \z \u** und verwenden Sie es als Switch-Parameter.

Beachten Sie, dass **Inhaltstabelle einfügen** fügt nur ein Inhaltsverzeichnisfeld ein, aber erstellt nicht wirklich das Inhaltsverzeichnis. Das Inhaltsverzeichnis wird von Microsoft Word erstellt, wenn das Feld aktualisiert wird.

Wenn Sie mit dieser Methode ein Inhaltsverzeichnis einfügen und dann die Datei in Microsoft Word öffnen, sehen Sie das Inhaltsverzeichnis nicht, da das Inhaltsverzeichnis-Feld noch nicht aktualisiert wurde.

In Microsoft Word werden Felder nicht automatisch aktualisiert, wenn ein Dokument geöffnet wird, , aber Sie können Felder in einem Dokument jederzeit aktualisieren, indem Sie F9 drücken.

### Beispiele

Zeigt, wie Sie ein Inhaltsverzeichnis (TOC) in ein Dokument einfügen, indem Sie Überschriftenstile als Einträge verwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein Inhaltsverzeichnis für die erste Seite des Dokuments einfügen.
// Konfigurieren Sie die Tabelle, um Absätze mit Überschriften der Ebenen 1 bis 3 aufzunehmen.
// Legen Sie außerdem seine Einträge als Hyperlinks fest, die uns führen
// an die Position der Überschrift, wenn in Microsoft Word mit der linken Maustaste geklickt wird.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Füllen Sie das Inhaltsverzeichnis, indem Sie Absätze mit Überschriftenstilen hinzufügen.
// Jede solche Überschrift mit einer Ebene zwischen 1 und 3 erstellt einen Eintrag in der Tabelle.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// Ein Inhaltsverzeichnis ist ein Feld eines Typs, der aktualisiert werden muss, um ein aktuelles Ergebnis anzuzeigen.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### Siehe auch

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


