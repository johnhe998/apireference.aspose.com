---
title: Enum ShapeLineStyle
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.ShapeLineStyle enum. Specifica lo stile della linea composta di aShape .
type: docs
weight: 1120
url: /it/net/aspose.words.drawing/shapelinestyle/
---
## ShapeLineStyle enumeration

Specifica lo stile della linea composta di a[`Shape`](../shape/) .

```csharp
public enum ShapeLineStyle
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Single | `0` | Riga singola. |
| Double | `1` | Linee doppie di uguale larghezza. |
| ThickThin | `2` | Linee doppie, una spessa, una sottile. |
| ThinThick | `3` | Linee doppie, una sottile, una spessa. |
| Triple | `4` | Tre linee, sottili, spesse, sottili. |
| Default | `0` | Il valore predefinito èSingle . |

### Esempi

Mostra come modificare le proprietà del tratto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// Le forme base, come il rettangolo, hanno due parti visibili.
// 1 - Il riempimento, che si applica all'area all'interno del contorno della forma:
shape.Fill.ForeColor = Color.White;

// 2 - Il tratto, che segna il contorno della forma:
// Modifica varie proprietà del tratto di questa forma.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### Guarda anche

* property [LineStyle](../stroke/linestyle/)
* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


