---
title: Table.VerticalAnchor
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft das Basisobjekt ab aus dem die vertikale Positionierung der schwebenden Tabelle berechnet werden soll. Standardwert istMargin .
type: docs
weight: 340
url: /de/net/aspose.words.tables/table/verticalanchor/
---
## Table.VerticalAnchor property

Ruft das Basisobjekt ab, aus dem die vertikale Positionierung der schwebenden Tabelle berechnet werden soll. Standardwert istMargin .

```csharp
public RelativeVerticalPosition VerticalAnchor { get; set; }
```

### Beispiele

Zeigt, wie Sie mit Floating-Tables-Eigenschaften arbeiten.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // Nur Margin, Page, Column verfügbar in RelativeHorizontalPosition für HorizontalAnchor Setter.
    // Die ArgumentException wird für alle anderen Werte ausgelöst.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // Nur Rand, Seite, Absatz verfügbar in RelativeVerticalPosition für VerticalAnchor-Setter.
    // Die ArgumentException wird für alle anderen Werte ausgelöst.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### Siehe auch

* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


