---
title: RevisionOptions.ShowRevisionBars
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionOptions propiedad. Permite especificar si las barras de revisión deben representarse cerca de las líneas que contienen contenido revisado. El valor predeterminado es Verdadero.
type: docs
weight: 180
url: /es/net/aspose.words.layout/revisionoptions/showrevisionbars/
---
## RevisionOptions.ShowRevisionBars property

Permite especificar si las barras de revisión deben representarse cerca de las líneas que contienen contenido revisado. El valor predeterminado es Verdadero.

```csharp
public bool ShowRevisionBars { get; set; }
```

### Ejemplos

Muestra cómo modificar la apariencia de las revisiones en un documento de salida renderizado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte una revisión, luego cambie el color de todas las revisiones a verde.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Elimina la barra que aparece a la izquierda de cada línea revisada.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Ver también

* class [RevisionOptions](../)
* espacio de nombres [Aspose.Words.Layout](../../revisionoptions/)
* asamblea [Aspose.Words](../../../)


