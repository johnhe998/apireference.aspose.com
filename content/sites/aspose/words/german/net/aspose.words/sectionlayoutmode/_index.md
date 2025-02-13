---
title: Enum SectionLayoutMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.SectionLayoutMode opsomming. Gibt den Layoutmodus für einen Abschnitt an der es ermöglicht das Dokumentrasterverhalten zu definieren.
type: docs
weight: 5460
url: /de/net/aspose.words/sectionlayoutmode/
---
## SectionLayoutMode enumeration

Gibt den Layoutmodus für einen Abschnitt an, der es ermöglicht, das Dokumentrasterverhalten zu definieren.

```csharp
public enum SectionLayoutMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Default | `0` | Gibt an, dass kein Dokumentraster auf den Inhalt des entsprechenden Abschnitts im Dokument angewendet werden soll. |
| Grid | `1` | Gibt an, dass der entsprechende Abschnitt sowohl den zusätzlichen Zeilenabstand als auch den Zeichenabstand zu jeder Zeile und jedem Zeichen darin hinzugefügt haben soll, um eine bestimmte Anzahl von Zeilen pro Seite und Zeichen pro Zeile beizubehalten. Zeichen werden nicht automatisch an Gitterlinien ausgerichtet Eingabe. |
| LineGrid | `2` | Gibt an, dass im entsprechenden Abschnitt jeder Zeile innerhalb des entsprechenden Abschnitts ein zusätzlicher Zeilenabstand hinzugefügt werden soll , um die angegebene Anzahl von Zeilen pro Seite beizubehalten. |
| SnapToChars | `3` | Gibt an, dass der entsprechende Abschnitt sowohl den zusätzlichen Zeilenabstand als auch den Zeichenabstand zu jeder Zeile und jedem darin enthaltenen Zeichen hinzugefügt haben soll, um eine bestimmte Anzahl von Zeilen pro Seite und Zeichen pro Zeile beizubehalten. Zeichen werden beim Tippen automatisch an Gitterlinien ausgerichtet. |

### Beispiele

Zeigt, wie man a für die Anzahl der Zeichen angibt, die jede Zeile haben darf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aktivieren Sie Pitching und verwenden Sie es dann, um die Anzahl der Zeichen pro Zeile in diesem Abschnitt festzulegen.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// Die Anzahl der Zeichen hängt auch von der Schriftgröße ab.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

Zeigt, wie Sie ein Limit für die Anzahl der Zeilen angeben, die jede Seite haben darf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aktivieren Sie Pitching und verwenden Sie es dann, um die Anzahl der Zeilen pro Seite in diesem Abschnitt festzulegen.
// Eine ausreichend große Schriftgröße verschiebt einige Zeilen nach unten auf die nächste Seite, um überlappende Zeichen zu vermeiden.
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


