---
title: Class GradientStopCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.GradientStopCollection classe. Contiene una raccolta diGradientStop oggetti.
type: docs
weight: 860
url: /it/net/aspose.words.drawing/gradientstopcollection/
---
## GradientStopCollection class

Contiene una raccolta di[`GradientStop`](../gradientstop/) oggetti.

```csharp
public class GradientStopCollection : IEnumerable<GradientStop>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.drawing/gradientstopcollection/count/) { get; } | Ottiene un valore intero che indica il numero di elementi nella raccolta. |
| [Item](../../aspose.words.drawing/gradientstopcollection/item/) { get; set; } | Ottiene o imposta a[`GradientStop`](../gradientstop/) oggetto nella raccolta. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words.drawing/gradientstopcollection/add/)(GradientStop) | Aggiunge uno specificato[`GradientStop`](../gradientstop/) a una sfumatura. |
| [GetEnumerator](../../aspose.words.drawing/gradientstopcollection/getenumerator/)() | Restituisce un enumeratore che scorre la raccolta. |
| [Insert](../../aspose.words.drawing/gradientstopcollection/insert/)(int, GradientStop) | Inserisce a[`GradientStop`](../gradientstop/) alla raccolta in un determinato indice. |
| [Remove](../../aspose.words.drawing/gradientstopcollection/remove/)(GradientStop) | Rimuove uno specificato[`GradientStop`](../gradientstop/) dalla collezione. |
| [RemoveAt](../../aspose.words.drawing/gradientstopcollection/removeat/)(int) | Rimuove a[`GradientStop`](../gradientstop/)dalla raccolta a un indice specificato. |

### Osservazioni

Non crei direttamente istanze di questa classe. Usa il[`GradientStops`](../fill/gradientstops/) proprietà per accedere alle interruzioni del gradiente degli oggetti di riempimento.

### Esempi

Mostra come aggiungere interruzioni di sfumatura al riempimento sfumato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// Ottieni la raccolta delle interruzioni del gradiente.
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// Cambia la prima fermata del gradiente.
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// Aggiunge una nuova interruzione del gradiente alla fine della raccolta.
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// Rimuove l'arresto del gradiente all'indice 1.
gradientStops.RemoveAt(1);
// E inserisci una nuova fermata del gradiente allo stesso indice 1.
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// Rimuovi l'ultima fermata del gradiente nella raccolta.
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// Usa l'opzione di conformità per definire la forma usando DML
// se vuoi ottenere la proprietà "GradientStops" dopo il salvataggio del documento.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### Guarda anche

* class [GradientStop](../gradientstop/)
* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


