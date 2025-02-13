---
title: Enum RelativeVerticalPosition
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.RelativeVerticalPosition opsomming. Gibt an zu was die vertikale Position einer Form oder eines Textrahmens relativ ist.
type: docs
weight: 1070
url: /de/net/aspose.words.drawing/relativeverticalposition/
---
## RelativeVerticalPosition enumeration

Gibt an, zu was die vertikale Position einer Form oder eines Textrahmens relativ ist.

```csharp
public enum RelativeVerticalPosition
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Margin | `0` | Gibt an, dass die vertikale Positionierung relativ zu den Seitenrändern erfolgen soll. |
| Page | `1` | Das Objekt wird relativ zum oberen Seitenrand positioniert. |
| Paragraph | `2` | Das Objekt wird relativ zum oberen Rand des Absatzes positioniert, der den Anker enthält. |
| Line | `3` | Undokumentiert. |
| TopMargin | `4` | Gibt an, dass die vertikale Positionierung relativ zum oberen Rand der aktuellen Seite erfolgen soll. |
| BottomMargin | `5` | Gibt an, dass die vertikale Positionierung relativ zum unteren Rand der aktuellen Seite erfolgen soll. |
| InsideMargin | `6` | Gibt an, dass die vertikale Positionierung relativ zum Innenrand der aktuellen Seite erfolgen soll. |
| OutsideMargin | `7` | Gibt an, dass die vertikale Positionierung relativ zum Außenrand der aktuellen Seite erfolgen soll. |
| TableDefault | `0` | Standardwert istMargin . |
| TextFrameDefault | `2` | Standardwert istParagraph . |

### Beispiele

Zeigt, wie ein schwebendes Bild in der Mitte einer Seite eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein, das hinter dem überlappenden Text angezeigt wird, und richten Sie es an der Mitte der Seite aus.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

Zeigt, wie ein Bild eingefügt und als Wasserzeichen verwendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Bild in die Kopfzeile ein, damit es auf jeder Seite sichtbar ist.
Image image = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
Shape shape = builder.InsertImage(image);
shape.WrapType = WrapType.None;
shape.BehindText = true;

// Platzieren Sie das Bild in der Mitte der Seite.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermark.docx");
```

Zeigt, wie ein Bild eingefügt und als Wasserzeichen verwendet wird (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Bild in die Kopfzeile ein, damit es auf jeder Seite sichtbar ist.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

using (SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png"))
{
    builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
    Shape shape = builder.InsertImage(image);
    shape.WrapType = WrapType.None;
    shape.BehindText = true;

    // Platzieren Sie das Bild in der Mitte der Seite.
    shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
    shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
    shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
    shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermarkNetStandard2.docx");
```

### Siehe auch

* property [RelativeVerticalPosition](../shapebase/relativeverticalposition/)
* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


