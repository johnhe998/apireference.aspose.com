---
title: ImageData.CropLeft
second_title: Aspose.Words für .NET-API-Referenz
description: ImageData eigendom. Definiert den Anteil der Bildentfernung von der linken Seite.
type: docs
weight: 70
url: /de/net/aspose.words.drawing/imagedata/cropleft/
---
## ImageData.CropLeft property

Definiert den Anteil der Bildentfernung von der linken Seite.

```csharp
public double CropLeft { get; set; }
```

### Bemerkungen

Der Zuschneidebetrag kann zwischen -1,0 und 1,0 liegen. Der Standardwert ist 0. Beachten Sie , dass ein Wert von 1 überhaupt kein Bild anzeigt. Negative Werte führen dazu, dass das Bild von der beschnittenen Kante nach innen gestaucht wird (der leere Raum zwischen dem Bild und der beschnittenen Kante wird mit der Füllfarbe der -Form gefüllt). Positive Werte kleiner als 1 führen dazu, dass das verbleibende Bild gestreckt wird, um es an die Form anzupassen.

Der Standardwert ist 0.

### Beispiele

Zeigt, wie die Bilddaten einer Form bearbeitet werden.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");
Shape sourceShape = (Shape)imgSourceDoc.GetChildNodes(NodeType.Shape, true)[0];

Document dstDoc = new Document();

// Eine Form aus dem Quelldokument importieren und an den ersten Absatz anhängen.
Shape importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

// Die importierte Form enthält ein Bild. Über das ImageData-Objekt können wir auf die Eigenschaften und Rohdaten des Bildes zugreifen.
ImageData imageData = importedShape.ImageData;
imageData.Title = "Imported Image";

Assert.True(imageData.HasImage);

// Wenn ein Bild keine Ränder hat, definiert sein ImageData-Objekt die Randfarbe als leer.
Assert.AreEqual(4, imageData.Borders.Count);
Assert.AreEqual(Color.Empty, imageData.Borders[0].Color);

// Dieses Bild ist nicht mit einer anderen Form- oder Bilddatei im lokalen Dateisystem verknüpft.
Assert.False(imageData.IsLink);
Assert.False(imageData.IsLinkOnly);

// Die Eigenschaften "Helligkeit" und "Kontrast" definieren Bildhelligkeit und Kontrast
// auf einer Skala von 0-1, mit dem Standardwert bei 0,5.
imageData.Brightness = 0.8;
imageData.Contrast = 1.0;

// Die obigen Helligkeits- und Kontrastwerte haben ein Bild mit viel Weiß erzeugt.
// Wir können eine Farbe mit der ChromaKey-Eigenschaft auswählen, um sie durch Transparenz zu ersetzen, z. B. Weiß.
imageData.ChromaKey = Color.White;

// Importiere die Quellform erneut und setze das Bild auf Monochrom.
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.GrayScale = true;

// Importieren Sie die Quellform erneut, um ein drittes Bild zu erstellen, und setzen Sie es auf BiLevel.
// BiLevel setzt jedes Pixel entweder auf Schwarz oder Weiß, je nachdem, was näher an der Originalfarbe liegt.
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.BiLevel = true;

// Zuschneiden wird auf einer Skala von 0-1 bestimmt. Beschneiden einer Seite um 0,3
// 30 % des Bildes werden an der beschnittenen Seite abgeschnitten.
importedShape.ImageData.CropBottom = 0.3;
importedShape.ImageData.CropLeft = 0.3;
importedShape.ImageData.CropTop = 0.3;
importedShape.ImageData.CropRight = 0.3;

dstDoc.Save(ArtifactsDir + "Drawing.ImageData.docx");
```

### Siehe auch

* class [ImageData](../)
* namensraum [Aspose.Words.Drawing](../../imagedata/)
* Montage [Aspose.Words](../../../)


