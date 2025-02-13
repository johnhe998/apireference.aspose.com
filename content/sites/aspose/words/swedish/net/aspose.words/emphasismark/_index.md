---
title: Enum EmphasisMark
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.EmphasisMark uppräkning. Anger möjliga typer av betoningsmärke.
type: docs
weight: 1310
url: /sv/net/aspose.words/emphasismark/
---
## EmphasisMark enumeration

Anger möjliga typer av betoningsmärke.

```csharp
public enum EmphasisMark
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| None | `0` | Ingen betoning. |
| OverSolidCircle | `1` | Betoningen är en hel svart cirkel som visas ovanför texten. |
| OverComma | `2` | Betoningen är ett kommatecken som visas ovanför texten. |
| OverWhiteCircle | `3` | Betoningen är en tom vit cirkel som visas ovanför texten. |
| UnderSolidCircle | `4` | Betoningen är en hel svart cirkel som visas under texten. |

### Exempel

Visar hur man lägger till ytterligare tecken renderat ovanför/under tecknet.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Möjliga typer av betoningsmärke:
// https://apireference.aspose.com/words/net/aspose.words/emphasismark
builder.Font.EmphasisMark = emphasisMark; 

builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");

builder.Document.Save(ArtifactsDir + "Fonts.SetEmphasisMark.docx");
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


