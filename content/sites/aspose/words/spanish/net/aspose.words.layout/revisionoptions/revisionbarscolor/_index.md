---
title: RevisionOptions.RevisionBarsColor
second_title: Referencia de API de Aspose.Words para .NET
description: RevisionOptions propiedad. Permite especificar el color que se utilizará para las barras laterales que identifican las líneas del documento que contienen información revisada. El valor predeterminado esRed .
type: docs
weight: 130
url: /es/net/aspose.words.layout/revisionoptions/revisionbarscolor/
---
## RevisionOptions.RevisionBarsColor property

Permite especificar el color que se utilizará para las barras laterales que identifican las líneas del documento que contienen información revisada. El valor predeterminado esRed .

```csharp
public RevisionColor RevisionBarsColor { get; set; }
```

### Observaciones

Estableciendo esta propiedad enByAuthor oNoHighlight valores dará como resultado que se oculten las barras de revisión del diseño.

### Ejemplos

Muestra cómo modificar la apariencia de las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Obtener el objeto RevisionOptions que controla la apariencia de las revisiones.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Representar las revisiones de inserción en verde y cursiva.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Presentar las revisiones de eliminación en rojo y en negrita.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// El mismo texto aparecerá dos veces en una revisión de movimiento:
// una vez en el punto de partida y una vez en el destino de llegada.
// Representar el texto en amarillo en la revisión desde la que se movió con un doble tachado
// y doble subrayado azul en la revisión a la que se movió.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Renderizar las revisiones del formato en rojo oscuro y en negrita.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Coloque una barra gruesa de color azul oscuro en el lado izquierdo de la página junto a las líneas afectadas por las revisiones.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Mostrar marcas de revisión y texto original.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Obtenga movimiento, eliminación, revisiones de formato y comentarios para mostrar en globos verdes
// en el lado derecho de la página.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Estas funciones solo se aplican a formatos como .pdf o .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Ver también

* enum [RevisionColor](../../revisioncolor/)
* class [RevisionOptions](../)
* espacio de nombres [Aspose.Words.Layout](../../revisionoptions/)
* asamblea [Aspose.Words](../../../)


