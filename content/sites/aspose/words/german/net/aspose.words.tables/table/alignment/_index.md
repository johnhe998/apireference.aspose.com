---
title: Table.Alignment
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Gibt an wie eine InlineTabelle im Dokument ausgerichtet wird.
type: docs
weight: 40
url: /de/net/aspose.words.tables/table/alignment/
---
## Table.Alignment property

Gibt an, wie eine Inline-Tabelle im Dokument ausgerichtet wird.

```csharp
public TableAlignment Alignment { get; set; }
```

### Bemerkungen

Der Standardwert istLeft.

### Beispiele

Zeigt, wie Sie einen Gliederungsrahmen auf eine Tabelle anwenden.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Richten Sie die Tabelle an der Mitte der Seite aus.
table.Alignment = TableAlignment.Center;

// Löschen Sie alle vorhandenen Rahmen und Schattierungen aus der Tabelle.
table.ClearBorders();
table.ClearShading();

// Fügen Sie dem Umriss der Tabelle grüne Ränder hinzu.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Füllen Sie die Zellen mit einer hellgrünen Volltonfarbe.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Siehe auch

* enum [TableAlignment](../../tablealignment/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


