---
title: Shape.HorizontalRuleFormat
second_title: Aspose.Words für .NET-API-Referenz
description: Shape eigendom. Bietet Zugriff auf die Eigenschaften der Form der horizontalen Linie. Gibt für eine Form die keine horizontale Linie ist null zurück.
type: docs
weight: 100
url: /de/net/aspose.words.drawing/shape/horizontalruleformat/
---
## Shape.HorizontalRuleFormat property

Bietet Zugriff auf die Eigenschaften der Form der horizontalen Linie. Gibt für eine Form, die keine horizontale Linie ist, null zurück.

```csharp
public HorizontalRuleFormat HorizontalRuleFormat { get; }
```

### Beispiele

Zeigt, wie Sie eine horizontale Linienform einfügen und ihre Formatierung anpassen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

Assert.True(shape.IsHorizontalRule);
Assert.True(shape.HorizontalRuleFormat.NoShade);
```

### Siehe auch

* class [HorizontalRuleFormat](../../horizontalruleformat/)
* class [Shape](../)
* namensraum [Aspose.Words.Drawing](../../shape/)
* Montage [Aspose.Words](../../../)


