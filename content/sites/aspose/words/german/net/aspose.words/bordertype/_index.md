---
title: Enum BorderType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.BorderType opsomming. Gibt Seiten eines Rahmens an.
type: docs
weight: 90
url: /de/net/aspose.words/bordertype/
---
## BorderType enumeration

Gibt Seiten eines Rahmens an.

```csharp
public enum BorderType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `-1` | Standardwert. |
| Bottom | `0` | Gibt den unteren Rand eines Absatzes oder einer Tabellenzelle an. |
| Left | `1` | Gibt den linken Rand eines Absatzes oder einer Tabellenzelle an. |
| Right | `2` | Gibt den rechten Rand eines Absatzes oder einer Tabellenzelle an. |
| Top | `3` | Gibt den oberen Rand eines Absatzes oder einer Tabellenzelle an. |
| Horizontal | `4` | Gibt die horizontale Grenze zwischen Zellen in einer Tabelle oder zwischen übereinstimmenden Absätzen an. |
| Vertical | `5` | Gibt den vertikalen Rand zwischen Zellen in einer Tabelle an. |
| DiagonalDown | `6` | Gibt den diagonalen Rahmen in einer Tabellenzelle an. |
| DiagonalUp | `7` | Gibt den diagonalen Rahmen in einer Tabellenzelle an. |

### Beispiele

Zeigt, wie Sie einen Absatz mit einem oberen Rand einfügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


