---
title: Enum WrapType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.WrapType opsomming. Gibt an wie Text um eine Form oder ein Bild gewickelt wird.
type: docs
weight: 1250
url: /de/net/aspose.words.drawing/wraptype/
---
## WrapType enumeration

Gibt an, wie Text um eine Form oder ein Bild gewickelt wird.

```csharp
public enum WrapType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `3` | Kein Textumbruch um die Form. Die Form wird hinter oder vor Text platziert. |
| Inline | `0` | Die Form bleibt auf derselben Ebene wie Text und wird als Zeichen behandelt. |
| TopBottom | `1` | Der Text endet am oberen Rand der Form und beginnt in der Zeile unterhalb der Form neu. |
| Square | `2` | Fliesst Text um alle Seiten des quadratischen Begrenzungsrahmens der Form herum. |
| Tight | `4` | Wickelt sich eng um die Kanten der Form, anstatt um den Begrenzungsrahmen. |
| Through | `5` | Dasselbe wie Tight, aber wickelt sich in alle Teile der Form, die offen sind. |

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

* property [WrapType](../shapebase/wraptype/)
* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


