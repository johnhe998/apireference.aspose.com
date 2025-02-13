---
title: Class FrameFormat
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.FrameFormat klas. Repräsentiert rahmenbezogene Formatierung für einen Absatz.
type: docs
weight: 2890
url: /de/net/aspose.words/frameformat/
---
## FrameFormat class

Repräsentiert rahmenbezogene Formatierung für einen Absatz.

```csharp
public class FrameFormat
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Height](../../aspose.words/frameformat/height/) { get; } | Ruft die Höhe des angegebenen Rahmens ab. |
| [HeightRule](../../aspose.words/frameformat/heightrule/) { get; } | Ruft die Regel zur Bestimmung der Höhe des angegebenen Rahmens ab. |
| [HorizontalAlignment](../../aspose.words/frameformat/horizontalalignment/) { get; } | Ruft die horizontale Ausrichtung des angegebenen Rahmens ab. |
| [HorizontalDistanceFromText](../../aspose.words/frameformat/horizontaldistancefromtext/) { get; } | Ruft den horizontalen Abstand zwischen einem Rahmen und dem umgebenden Text in Punkt ab. |
| [HorizontalPosition](../../aspose.words/frameformat/horizontalposition/) { get; } | Ruft den horizontalen Abstand zwischen dem Rand des Rahmens und dem durch den angegebenen Gegenstand ab[`RelativeHorizontalPosition`](./relativehorizontalposition/) Eigentum. |
| [IsFrame](../../aspose.words/frameformat/isframe/) { get; } | Gibt wahr zurück, wenn der Absatz ein Rahmen ist. |
| [RelativeHorizontalPosition](../../aspose.words/frameformat/relativehorizontalposition/) { get; } | Ruft die relative horizontale Position eines Rahmens ab. |
| [RelativeVerticalPosition](../../aspose.words/frameformat/relativeverticalposition/) { get; } | Ruft die relative vertikale Position eines Rahmens ab. |
| [VerticalAlignment](../../aspose.words/frameformat/verticalalignment/) { get; } | Ruft die vertikale Ausrichtung des angegebenen Rahmens ab. |
| [VerticalDistanceFromText](../../aspose.words/frameformat/verticaldistancefromtext/) { get; } | Gibt den vertikalen Abstand (in Punkten) zwischen einem Rahmen und dem umgebenden Text an. |
| [VerticalPosition](../../aspose.words/frameformat/verticalposition/) { get; } | Ruft den vertikalen Abstand zwischen dem Rand des Rahmens und dem durch den angegebenen Gegenstand ab[`RelativeVerticalPosition`](./relativeverticalposition/) Eigentum. |
| [Width](../../aspose.words/frameformat/width/) { get; } | Ruft die Breite des angegebenen Rahmens in Punkten ab. |

### Bemerkungen

Dieses Objekt wird immer erstellt. Wenn ein Absatz ein Rahmen ist, enthalten alle Eigenschaften entsprechende Werte, andernfalls werden alle Eigenschaften auf ihre Standardwerte gesetzt.

Verwenden[`IsFrame`](./isframe/) um zu prüfen, ob Absatz ein Rahmen ist.

### Beispiele

Zeigt, wie Informationen zu Formatierungseigenschaften von Absätzen abgerufen werden, die Rahmen sind.

```csharp
Document doc = new Document(MyDir + "Paragraph frame.docx");

Paragraph paragraphFrame = doc.FirstSection.Body.Paragraphs.OfType<Paragraph>().First(p => p.FrameFormat.IsFrame);

Assert.AreEqual(233.3d, paragraphFrame.FrameFormat.Width);
Assert.AreEqual(138.8d, paragraphFrame.FrameFormat.Height);
Assert.AreEqual(HeightRule.AtLeast, paragraphFrame.FrameFormat.HeightRule);
Assert.AreEqual(HorizontalAlignment.Default, paragraphFrame.FrameFormat.HorizontalAlignment);
Assert.AreEqual(VerticalAlignment.Default, paragraphFrame.FrameFormat.VerticalAlignment);
Assert.AreEqual(34.05d, paragraphFrame.FrameFormat.HorizontalPosition);
Assert.AreEqual(RelativeHorizontalPosition.Page, paragraphFrame.FrameFormat.RelativeHorizontalPosition);
Assert.AreEqual(9.0d, paragraphFrame.FrameFormat.HorizontalDistanceFromText);
Assert.AreEqual(20.5d, paragraphFrame.FrameFormat.VerticalPosition);
Assert.AreEqual(RelativeVerticalPosition.Paragraph, paragraphFrame.FrameFormat.RelativeVerticalPosition);
Assert.AreEqual(0.0d, paragraphFrame.FrameFormat.VerticalDistanceFromText);
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


