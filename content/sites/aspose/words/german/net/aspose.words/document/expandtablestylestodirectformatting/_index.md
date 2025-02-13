---
title: Document.ExpandTableStylesToDirectFormatting
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Wandelt die in Tabellenstilen angegebene Formatierung in direkte Formatierung für Tabellen im Dokument um.
type: docs
weight: 570
url: /de/net/aspose.words/document/expandtablestylestodirectformatting/
---
## Document.ExpandTableStylesToDirectFormatting method

Wandelt die in Tabellenstilen angegebene Formatierung in direkte Formatierung für Tabellen im Dokument um.

```csharp
public void ExpandTableStylesToDirectFormatting()
```

### Bemerkungen

Diese Methode existiert, weil diese Version von Aspose.Words nur eingeschränkte Unterstützung für -Tabellenstile bietet (siehe unten). Diese Methode kann hilfreich sein, wenn Sie ein DOCX- oder WordprocessingML -Dokument laden, das Tabellen enthält, die mit Tabellenstilen formatiert sind, und Sie die Formatierung von -Tabellen, -Zellen, -Absätzen oder -Text abfragen müssen.

Diese Version von Aspose.Words bietet eingeschränkte Unterstützung für Tabellenstile wie folgt:

* In DOCX- oder WordprocessingML-Dokumenten definierte Tabellenstile werden als Tabellenstile beibehalten, wenn das Dokument als DOCX- oder WordprocessingML gespeichert wird.
* Tabellenstile, die in DOCX- oder WordprocessingML-Dokumenten definiert sind, werden automatisch konvertiert in die direkte Formatierung von Tabellen, wenn das Dokument in einem anderen Format gespeichert, gerendert oder gedruckt wird.
* In DOC-Dokumenten definierte Tabellenstile werden als Tabellenstile beibehalten, wenn das Dokument nur als DOC gespeichert wird.

### Beispiele

Zeigt, wie die Eigenschaften eines Tabellenstils direkt auf die Elemente der Tabelle angewendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// Diese Methode betrifft Tabellenstileigenschaften wie die, die wir oben festgelegt haben.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


