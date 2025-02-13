---
title: ParagraphFormat.LineSpacing
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft den Zeilenabstand in Punkten für den Absatz ab oder legt ihn fest.
type: docs
weight: 180
url: /de/net/aspose.words/paragraphformat/linespacing/
---
## ParagraphFormat.LineSpacing property

Ruft den Zeilenabstand (in Punkten) für den Absatz ab oder legt ihn fest.

```csharp
public double LineSpacing { get; set; }
```

### Bemerkungen

Wenn die LineSpacingRule-Eigenschaft auf AtLeast festgelegt ist, kann der Zeilenabstand größer oder gleich sein, aber niemals kleiner als der angegebene LineSpacing-Wert.

Wenn die Eigenschaft „LineSpacingRule“ auf „Exactly“ gesetzt ist, ändert sich der Zeilenabstand niemals von dem angegebenen LineSpacing-Wert, selbst wenn innerhalb des Absatzes eine größere Schriftart verwendet wird.

### Beispiele

Zeigt, wie mit dem Zeilenabstand gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Unten sind drei Zeilenabstandsregeln, die wir mit definieren können
// "LineSpacingRule"-Eigenschaft des Absatzes, um den Abstand zwischen den Absätzen zu konfigurieren.
// 1 - Legen Sie einen Mindestabstand fest.
// Dadurch werden Textzeilen beliebiger Größe vertikal aufgefüllt
// das ist zu klein, um die minimale Zeilenhöhe einzuhalten.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Genauen Abstand festlegen.
// Wenn Sie Schriftgrößen verwenden, die zu groß für den Abstand sind, wird der Text abgeschnitten.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Legen Sie den Abstand als Vielfaches des Standardzeilenabstands fest, der standardmäßig 12 Punkte beträgt.
// Diese Art von Abstand wird auf verschiedene Schriftgrößen skaliert.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


