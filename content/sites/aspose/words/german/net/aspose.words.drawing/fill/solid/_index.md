---
title: Fill.Solid
second_title: Aspose.Words für .NET-API-Referenz
description: Fill methode. Setzt die Füllung auf eine einheitliche Farbe.
type: docs
weight: 200
url: /de/net/aspose.words.drawing/fill/solid/
---
## Solid() {#solid}

Setzt die Füllung auf eine einheitliche Farbe.

```csharp
public void Solid()
```

### Bemerkungen

Verwenden Sie diese Methode, um eine der Füllungen wieder in eine durchgehende Füllung umzuwandeln.

### Siehe auch

* class [Fill](../)
* namensraum [Aspose.Words.Drawing](../../fill/)
* Montage [Aspose.Words](../../../)

---

## Solid(Color) {#solid_1}

Legt die Füllung auf eine angegebene einheitliche Farbe fest.

```csharp
public void Solid(Color color)
```

### Bemerkungen

Verwenden Sie diese Methode, um eine der Füllungen wieder in eine durchgehende Füllung umzuwandeln.

### Beispiele

Zeigt, wie Sie eine der Füllungen wieder in eine durchgehende Füllung umwandeln.

```csharp
Document doc = new Document(MyDir + "Two color gradient.docx");

// Holen Sie sich das Füllobjekt für die Schriftart des ersten Laufs.
Fill fill = doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.Fill;

// Fülleigenschaften der Schriftart prüfen.
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill is transparent at {0}%", fill.Transparency * 100);

// Ändern Sie den Füllungstyp in Solid mit einheitlicher grüner Farbe.
fill.Solid(Color.Green);
Console.WriteLine("\nThe fill is changed:");
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill transparency is {0}%", fill.Transparency * 100);

doc.Save(ArtifactsDir + "Drawing.FillSolid.docx");
```

### Siehe auch

* class [Fill](../)
* namensraum [Aspose.Words.Drawing](../../fill/)
* Montage [Aspose.Words](../../../)


