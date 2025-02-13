---
title: Fill.Patterned
second_title: Aspose.Words per .NET API Reference
description: Fill metodo. Imposta il riempimento specificato su un motivo.
type: docs
weight: 170
url: /it/net/aspose.words.drawing/fill/patterned/
---
## Patterned(PatternType) {#patterned}

Imposta il riempimento specificato su un motivo.

```csharp
public void Patterned(PatternType patternType)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| patternType | PatternType | [`PatternType`](../../patterntype/) |

### Esempi

Mostra come impostare il motivo per una forma.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Fill fill = shape.Fill;

Console.WriteLine("Pattern value is: {0}", fill.Pattern);

// Esistono diversi modi per specificare il riempimento di un motivo.
// 1 - Applica il motivo al riempimento della forma:
fill.Patterned(PatternType.DiagonalBrick);

// 2 - Applica il motivo con i colori di primo piano e di sfondo al riempimento della forma:
fill.Patterned(PatternType.DiagonalBrick, Color.Aqua, Color.Bisque);

doc.Save(ArtifactsDir + "Shape.FillPattern.docx");
```

### Guarda anche

* enum [PatternType](../../patterntype/)
* class [Fill](../)
* spazio dei nomi [Aspose.Words.Drawing](../../fill/)
* assemblea [Aspose.Words](../../../)

---

## Patterned(PatternType, Color, Color) {#patterned_1}

Imposta il riempimento specificato su un motivo.

```csharp
public void Patterned(PatternType patternType, Color foreColor, Color backColor)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| patternType | PatternType | [`PatternType`](../../patterntype/) |
| foreColor | Color | Il colore del riempimento in primo piano. |
| backColor | Color | Il colore del riempimento dello sfondo. |

### Esempi

Mostra come impostare il motivo per una forma.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Fill fill = shape.Fill;

Console.WriteLine("Pattern value is: {0}", fill.Pattern);

// Esistono diversi modi per specificare il riempimento di un motivo.
// 1 - Applica il motivo al riempimento della forma:
fill.Patterned(PatternType.DiagonalBrick);

// 2 - Applica il motivo con i colori di primo piano e di sfondo al riempimento della forma:
fill.Patterned(PatternType.DiagonalBrick, Color.Aqua, Color.Bisque);

doc.Save(ArtifactsDir + "Shape.FillPattern.docx");
```

### Guarda anche

* enum [PatternType](../../patterntype/)
* class [Fill](../)
* spazio dei nomi [Aspose.Words.Drawing](../../fill/)
* assemblea [Aspose.Words](../../../)


