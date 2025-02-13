---
title: ShapeBase.AlternativeText
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Definisce un testo alternativo da visualizzare invece di un grafico.
type: docs
weight: 20
url: /it/net/aspose.words.drawing/shapebase/alternativetext/
---
## ShapeBase.AlternativeText property

Definisce un testo alternativo da visualizzare invece di un grafico.

```csharp
public string AlternativeText { get; set; }
```

### Osservazioni

Il valore predefinito è una stringa vuota.

### Esempi

Mostra come utilizzare il testo alternativo di una forma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertShape(ShapeType.Cube, 150, 150);
shape.Name = "MyCube";

shape.AlternativeText = "Alt text for MyCube.";

// Possiamo accedere al testo alternativo di una forma facendo clic con il pulsante destro del mouse e quindi tramite "Formatta forma" -> "Testo alternativo".
doc.Save(ArtifactsDir + "Shape.AltText.docx");

// Salva il documento in HTML, quindi elimina l'immagine collegata che appartiene alla nostra forma.
// Il browser che sta leggendo il nostro HTML visualizzerà il testo alternativo al posto dell'immagine mancante.
doc.Save(ArtifactsDir + "Shape.AltText.html");
```

### Guarda anche

* class [ShapeBase](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shapebase/)
* assemblea [Aspose.Words](../../../)


