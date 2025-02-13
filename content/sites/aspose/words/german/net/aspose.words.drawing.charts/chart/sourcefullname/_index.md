---
title: Chart.SourceFullName
second_title: Aspose.Words für .NET-API-Referenz
description: Chart eigendom. Ruft den Pfad und Namen einer xls/xlsxDatei ab mit der dieses Diagramm verknüpft ist.
type: docs
weight: 60
url: /de/net/aspose.words.drawing.charts/chart/sourcefullname/
---
## Chart.SourceFullName property

Ruft den Pfad und Namen einer xls/xlsx-Datei ab, mit der dieses Diagramm verknüpft ist.

```csharp
public string SourceFullName { get; set; }
```

### Beispiele

Zeigt, wie der vollständige Name des externen xls/xlsx-Dokuments abgerufen wird, wenn das Diagramm verknüpft ist.

```csharp
Document doc = new Document(MyDir + "Shape with linked chart.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.True(shape.Chart.SourceFullName.Contains("Examples\\Data\\Spreadsheet.xlsx"));
```

### Siehe auch

* class [Chart](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chart/)
* Montage [Aspose.Words](../../../)


