---
title: ShapeBase.Name
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Ottiene o imposta il nome della forma opzionale.
type: docs
weight: 380
url: /it/net/aspose.words.drawing/shapebase/name/
---
## ShapeBase.Name property

Ottiene o imposta il nome della forma opzionale.

```csharp
public string Name { get; set; }
```

### Osservazioni

L'impostazione predefinita è una stringa vuota.

Non può essere null, ma può essere una stringa vuota.

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


