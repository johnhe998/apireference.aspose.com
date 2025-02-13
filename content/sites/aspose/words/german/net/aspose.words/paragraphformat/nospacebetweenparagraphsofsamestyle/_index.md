---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Wenn wahrSpaceBefore undSpaceAfter wird ignoriert zwischen den Absätzen des gleichen Stils.
type: docs
weight: 230
url: /de/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

Wenn wahr,[`SpaceBefore`](../spacebefore/) und[`SpaceAfter`](../spaceafter/) wird ignoriert zwischen den Absätzen des gleichen Stils.

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### Bemerkungen

Diese Einstellung wird nur wirksam, wenn sie auf ein Absatzformat angewendet wird. Wenn es direkt auf einen Absatz angewendet wird, hat es keine Wirkung.

### Beispiele

Zeigt, wie kein Abstand zwischen Absätzen mit demselben Stil angewendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einen großen Abstand vor und nach Absätzen anwenden, die dieser Builder erstellt.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Setzen Sie das Flag "NoSpaceBetweenParagraphsOfSameStyle" auf "true", um es anzuwenden
// kein Abstand zwischen Absätzen mit demselben Stil, wodurch ähnliche Absätze gruppiert werden.
// Lassen Sie das Flag "NoSpaceBetweenParagraphsOfSameStyle" auf "false"
// um gleichmäßige Abstände auf jeden Absatz anzuwenden.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


