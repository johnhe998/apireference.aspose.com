---
title: DocumentBuilder.InsertHorizontalRule
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Fügt eine horizontale Linienform in das Dokument ein.
type: docs
weight: 320
url: /de/net/aspose.words/documentbuilder/inserthorizontalrule/
---
## DocumentBuilder.InsertHorizontalRule method

Fügt eine horizontale Linienform in das Dokument ein.

```csharp
public Shape InsertHorizontalRule()
```

### Rückgabewert

Die Form, die eine horizontale Regel ist.

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

* class [Shape](../../../aspose.words.drawing/shape/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


