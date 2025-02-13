---
title: ParagraphFormat.SnapToGrid
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Gibt an ob der aktuelle Absatz beim Layout der Inhalte im Absatz die Einstellungen für Dokumentrasterlinien pro Seite verwenden soll.
type: docs
weight: 280
url: /de/net/aspose.words/paragraphformat/snaptogrid/
---
## ParagraphFormat.SnapToGrid property

Gibt an, ob der aktuelle Absatz beim Layout der Inhalte im Absatz die Einstellungen für Dokumentrasterlinien pro Seite verwenden soll.

```csharp
public bool SnapToGrid { get; set; }
```

### Beispiele

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

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


