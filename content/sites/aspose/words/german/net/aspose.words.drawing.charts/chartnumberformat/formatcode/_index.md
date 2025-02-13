---
title: ChartNumberFormat.FormatCode
second_title: Aspose.Words für .NET-API-Referenz
description: ChartNumberFormat eigendom. Ruft den auf eine Datenbeschriftung angewendeten Formatcode ab oder legt ihn fest.
type: docs
weight: 10
url: /de/net/aspose.words.drawing.charts/chartnumberformat/formatcode/
---
## ChartNumberFormat.FormatCode property

Ruft den auf eine Datenbeschriftung angewendeten Formatcode ab oder legt ihn fest.

```csharp
public string FormatCode { get; set; }
```

### Bemerkungen

Die Zahlenformatierung wird verwendet, um die Art und Weise zu ändern, wie ein Wert in einer Datenbeschriftung angezeigt wird, und kann auf sehr kreative Weise verwendet werden. Beispiele für Zahlenformate:

Zahl - "#,##0.00"

Währung - "\"$\"#,##0.00"

Uhrzeit – „[$-x-systime]h:mm:ss AM/PM“

Datum - "d/mm/yyyy"

Prozentsatz - "0,00 %"

Bruchteil - "# ?/?"

Wissenschaftlich - "0.00E+00"

Text - "@"

Buchhaltung - "_-\"$\"* #,##0.00_-;-\"$\"* #,##0.00_-;_-\"$\"* \"-\"??_ -;_-@_-"

Benutzerdefiniert mit Farbe - "[Red]-#,##0.0"

### Beispiele

Zeigt, wie Sie die Formatierung für Diagrammwerte festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Hinzufügen einer benutzerdefinierten Reihe zum Diagramm mit Kategorien für die X-Achse,
 // und große entsprechende numerische Werte für die Y-Achse.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Stellen Sie das Zahlenformat der Tick-Beschriftungen der Y-Achse so ein, dass Ziffern nicht mit Kommas gruppiert werden.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Dieses Flag kann den obigen Wert überschreiben und das Zahlenformat aus der Quellzelle ziehen.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

Zeigt, wie Datenbeschriftungen für eine Diagrammreihe aktiviert und konfiguriert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Füge ein Liniendiagramm hinzu und lösche dann seine Demo-Datenreihe, um mit einem sauberen Diagramm zu beginnen,
// und dann einen Titel setzen.
Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;
chart.Series.Clear();
chart.Title.Text = "Monthly sales report";

// Fügen Sie eine benutzerdefinierte Diagrammreihe mit Monaten als Kategorien für die X-Achse ein,
// und entsprechende Dezimalbeträge für die Y-Achse.
ChartSeries series = chart.Series.Add("Revenue", 
    new[] { "January", "February", "March" }, 
    new[] { 25.611d, 21.439d, 33.750d });

// Datenbeschriftungen aktivieren und dann ein benutzerdefiniertes Zahlenformat für die in den Datenbeschriftungen angezeigten Werte anwenden.
// Dieses Format behandelt angezeigte Dezimalwerte als Millionen von US-Dollar.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowValue = true;
dataLabels.NumberFormat.FormatCode = "\"US$\" #,##0.000\"M\"";

doc.Save(ArtifactsDir + "Charts.DataLabelNumberFormat.docx");
```

### Siehe auch

* class [ChartNumberFormat](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* Montage [Aspose.Words](../../../)


