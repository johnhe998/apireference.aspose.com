---
title: Document.RenderToScale
second_title: Aspose.Words för .NET API Referens
description: Document metod. Gör en dokumentsida till enGraphics objekt i en angiven skala.
type: docs
weight: 660
url: /sv/net/aspose.words/document/rendertoscale/
---
## Document.RenderToScale method

Gör en dokumentsida till enGraphics objekt i en angiven skala.

```csharp
public SizeF RenderToScale(int pageIndex, Graphics graphics, float x, float y, float scale)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| pageIndex | Int32 | Det 0-baserade sidindexet. |
| graphics | Graphics | Objektet där det ska renderas. |
| x | Single | X-koordinaten (i världsenheter) i det övre vänstra hörnet på den renderade sidan. |
| y | Single | Y-koordinaten (i världsenheter) i det övre vänstra hörnet på den renderade sidan. |
| scale | Single | Skalan för att rendera sidan (1,0 är 100%). |

### Returvärde

Bredden och höjden (i världsenheter) på den renderade sidan.

### Exempel

Visar hur de enskilda sidorna i ett dokument till grafik för att skapa en bild med miniatyrer av alla sidor.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Beräkna antalet rader och kolumner som vi kommer att fylla med miniatyrer.
const int thumbColumns = 2;
int thumbRows = Math.DivRem(doc.PageCount, thumbColumns, out int remainder);

if (remainder > 0)
    thumbRows++;

// Skala miniatyrerna i förhållande till storleken på den första sidan.
const float scale = 0.25f;
Size thumbSize = doc.GetPageInfo(0).GetSizeInPixels(scale, 96);

// Beräkna storleken på bilden som kommer att innehålla alla miniatyrer.
int imgWidth = thumbSize.Width * thumbColumns;
int imgHeight = thumbSize.Height * thumbRows;

using (Bitmap img = new Bitmap(imgWidth, imgHeight))
{
    using (Graphics gr = Graphics.FromImage(img))
    {
        gr.TextRenderingHint = TextRenderingHint.AntiAliasGridFit;

        // Fyll bakgrunden, som är genomskinlig som standard, med vitt.
        gr.FillRectangle(new SolidBrush(Color.White), 0, 0, imgWidth, imgHeight);

        for (int pageIndex = 0; pageIndex < doc.PageCount; pageIndex++)
        {
            int rowIdx = Math.DivRem(pageIndex, thumbColumns, out int columnIdx);

            // Ange var vi vill att miniatyrbilden ska visas.
            float thumbLeft = columnIdx * thumbSize.Width;
            float thumbTop = rowIdx * thumbSize.Height;

            // Gör en sida som en miniatyrbild och rama sedan in den i en rektangel av samma storlek.
            SizeF size = doc.RenderToScale(pageIndex, gr, thumbLeft, thumbTop, scale);
            gr.DrawRectangle(Pens.Black, thumbLeft, thumbTop, size.Width, size.Height);
        }

        img.Save(ArtifactsDir + "Rendering.Thumbnails.png");
    }
}
```

Återger enskilda sidor till grafik för att skapa en bild med miniatyrer av alla sidor (.NetStandard 2.0).

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Beräkna antalet rader och kolumner som vi kommer att fylla med miniatyrer.
const int thumbnailColumnsNum = 2;
int thumbRows = Math.DivRem(doc.PageCount, thumbnailColumnsNum, out int remainder);

if (remainder > 0)
    thumbRows++;

  // Skala miniatyrerna i förhållande till storleken på den första sidan.
const float scale = 0.25f;
Size thumbSize = doc.GetPageInfo(0).GetSizeInPixels(scale, 96);

// Beräkna storleken på bilden som kommer att innehålla alla miniatyrer.
int imgWidth = thumbSize.Width * thumbnailColumnsNum;
int imgHeight = thumbSize.Height * thumbRows;

using (SKBitmap bitmap = new SKBitmap(imgWidth, imgHeight))
{
    using (SKCanvas canvas = new SKCanvas(bitmap))
    {
        // Fyll bakgrunden, som är genomskinlig som standard, med vitt.
        canvas.Clear(SKColors.White);

        for (int pageIndex = 0; pageIndex < doc.PageCount; pageIndex++)
        {
            int rowIdx = Math.DivRem(pageIndex, thumbnailColumnsNum, out int columnIdx);

            // Ange var vi vill att miniatyrbilden ska visas.
            float thumbLeft = columnIdx * thumbSize.Width;
            float thumbTop = rowIdx * thumbSize.Height;

            SizeF size = doc.RenderToScale(pageIndex, canvas, thumbLeft, thumbTop, scale);

            // Gör en sida som en miniatyrbild och rama sedan in den i en rektangel av samma storlek.
            SKRect rect = new SKRect(0, 0, size.Width, size.Height);
            rect.Offset(thumbLeft, thumbTop);
            canvas.DrawRect(rect, new SKPaint
            {
                Color = SKColors.Black,
                Style = SKPaintStyle.Stroke
            });
        }

        using (SKFileWStream fs = new SKFileWStream(ArtifactsDir + "Rendering.CreateThumbnailsNetStandard2.png"))
        {
            bitmap.PeekPixels().Encode(fs, SKEncodedImageFormat.Png, 100);
        }
    }
}
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


