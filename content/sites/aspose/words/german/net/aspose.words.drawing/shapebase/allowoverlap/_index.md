---
title: ShapeBase.AllowOverlap
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob diese Form andere Formen überlappen kann.
type: docs
weight: 10
url: /de/net/aspose.words.drawing/shapebase/allowoverlap/
---
## ShapeBase.AllowOverlap property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob diese Form andere Formen überlappen kann.

```csharp
public bool AllowOverlap { get; set; }
```

### Bemerkungen

Diese Eigenschaft beeinflusst das Verhalten der Form in Microsoft Word. Aspose.Words ignoriert den Wert dieser Eigenschaft.

Diese Eigenschaft gilt nur für Shapes der obersten Ebene.

Der Standardwert ist **Stimmt**.

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

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


