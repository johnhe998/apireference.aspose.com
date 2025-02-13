---
title: Table.BottomPadding
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft den Abstand in Punkt ab oder legt ihn fest der unter dem Inhalt von Zellen hinzugefügt werden soll.
type: docs
weight: 90
url: /de/net/aspose.words.tables/table/bottompadding/
---
## Table.BottomPadding property

Ruft den Abstand (in Punkt) ab oder legt ihn fest, der unter dem Inhalt von Zellen hinzugefügt werden soll.

```csharp
public double BottomPadding { get; set; }
```

### Beispiele

Zeigt, wie das Auffüllen von Inhalten in einer Tabelle konfiguriert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndTable();

// Legen Sie für jede Zelle in der Tabelle den Abstand zwischen ihrem Inhalt und jedem ihrer Ränder fest. 
// Diese Tabelle behält den minimalen Füllabstand bei, indem Text umbrochen wird.
table.LeftPadding = 30;
table.RightPadding = 60;
table.TopPadding = 10;
table.BottomPadding = 90;
table.PreferredWidth = PreferredWidth.FromPoints(250);

doc.Save(ArtifactsDir + "DocumentBuilder.SetRowFormatting.docx");
```

### Siehe auch

* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


