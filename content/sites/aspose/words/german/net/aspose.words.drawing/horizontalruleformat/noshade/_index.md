---
title: HorizontalRuleFormat.NoShade
second_title: Aspose.Words für .NET-API-Referenz
description: HorizontalRuleFormat eigendom. Zeigt das Vorhandensein von 3DSchattierung für die horizontale Linie an. Wenn wahr dann ist die horizontale Linie ohne 3DSchattierung und es wird Volltonfarbe verwendet.
type: docs
weight: 40
url: /de/net/aspose.words.drawing/horizontalruleformat/noshade/
---
## HorizontalRuleFormat.NoShade property

Zeigt das Vorhandensein von 3D-Schattierung für die horizontale Linie an. Wenn wahr, dann ist die horizontale Linie ohne 3D-Schattierung und es wird Volltonfarbe verwendet.

```csharp
public bool NoShade { get; set; }
```

### Bemerkungen

Der Standardwert ist falsch.

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

* class [HorizontalRuleFormat](../)
* namensraum [Aspose.Words.Drawing](../../horizontalruleformat/)
* Montage [Aspose.Words](../../../)


