---
title: Class ConvertUtil
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.ConvertUtil klas. Bietet Hilfsfunktionen zum Umrechnen zwischen verschiedenen Maßeinheiten.
type: docs
weight: 350
url: /de/net/aspose.words/convertutil/
---
## ConvertUtil class

Bietet Hilfsfunktionen zum Umrechnen zwischen verschiedenen Maßeinheiten.

```csharp
public static class ConvertUtil
```

## Methoden

| Name | Beschreibung |
| --- | --- |
| static [InchToPoint](../../aspose.words/convertutil/inchtopoint/)(double) | Konvertiert Zoll in Punkte. |
| static [MillimeterToPoint](../../aspose.words/convertutil/millimetertopoint/)(double) | Wandelt Millimeter in Punkte um. |
| static [PixelToNewDpi](../../aspose.words/convertutil/pixeltonewdpi/)(double, double, double) | Konvertiert Pixel von einer Auflösung in eine andere. |
| static [PixelToPoint](../../aspose.words/convertutil/pixeltopoint/#pixeltopoint)(double) | Konvertiert Pixel in Punkte bei 96 dpi. |
| static [PixelToPoint](../../aspose.words/convertutil/pixeltopoint/#pixeltopoint_1)(double, double) | Konvertiert Pixel in Punkte mit der angegebenen Pixelauflösung. |
| static [PointToInch](../../aspose.words/convertutil/pointtoinch/)(double) | Konvertiert Punkte in Zoll. |
| static [PointToPixel](../../aspose.words/convertutil/pointtopixel/#pointtopixel)(double) | Konvertiert Punkte in Pixel bei 96 dpi. |
| static [PointToPixel](../../aspose.words/convertutil/pointtopixel/#pointtopixel_1)(double, double) | Konvertiert Punkte in Pixel mit der angegebenen Pixelauflösung. |

### Beispiele

Zeigt, wie Papiergröße, Ausrichtung, Ränder und andere Einstellungen für einen Abschnitt angepasst werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.PageSetup.PaperSize = PaperSize.Legal;
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
builder.PageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);

builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PageSetup.PageMargins.docx");
```

Zeigt, wie Seiteneigenschaften in Zoll angegeben werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Das "Page Setup" eines Abschnitts definiert die Größe der Seitenränder in Punkt.
// Wir können auch die Klasse "ConvertUtil" verwenden, um eine vertrautere Maßeinheit zu verwenden,
// wie Zoll beim Definieren von Grenzen.
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(2.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(2.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);

// Ein Zoll sind 72 Punkte.
Assert.AreEqual(72.0d, ConvertUtil.InchToPoint(1));
Assert.AreEqual(1.0d, ConvertUtil.PointToInch(72));

// Inhalt hinzufügen, um die neuen Ränder zu demonstrieren.
builder.Writeln($"This Text is {pageSetup.LeftMargin} points/{ConvertUtil.PointToInch(pageSetup.LeftMargin)} inches from the left, " +
                $"{pageSetup.RightMargin} points/{ConvertUtil.PointToInch(pageSetup.RightMargin)} inches from the right, " +
                $"{pageSetup.TopMargin} points/{ConvertUtil.PointToInch(pageSetup.TopMargin)} inches from the top, " +
                $"and {pageSetup.BottomMargin} points/{ConvertUtil.PointToInch(pageSetup.BottomMargin)} inches from the bottom of the page.");

doc.Save(ArtifactsDir + "UtilityClasses.PointsAndInches.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


