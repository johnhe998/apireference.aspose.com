---
title: Enum RevisionColor
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Layout.RevisionColor enumeración. Permite especificar el color de las revisiones del documento.
type: docs
weight: 3180
url: /es/net/aspose.words.layout/revisioncolor/
---
## RevisionColor enumeration

Permite especificar el color de las revisiones del documento.

```csharp
public enum RevisionColor
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Auto | `0` | Predeterminado. |
| Black | `1` | Representa 000000 color. |
| Blue | `2` | Representa 2e97d3 color. |
| BrightGreen | `3` | Representa 84a35b color. |
| ClassicBlue | `4` | Representa 0000ff color. |
| ClassicRed | `5` | Representa ff0000 color. |
| DarkBlue | `6` | Representa 376e96 color. |
| DarkRed | `7` | Representa 881824 colores. |
| DarkYellow | `8` | Representa e09a2b color. |
| Gray25 | `9` | Representa a0a3a9 color. |
| Gray50 | `10` | Representa 50565e color. |
| Green | `11` | Representa 2c6234 color. |
| Pink | `12` | Representa color ce338f. |
| Red | `13` | Representa el color b5082e. |
| Teal | `14` | Representa el color de la cabina 1b9. |
| Turquoise | `15` | Representa 3eafc2 color. |
| Violet | `16` | Representa 633277 colores. |
| White | `17` | Representa el color ffffff. |
| Yellow | `18` | Representa el color de moda272. |
| NoHighlight | `19` | No se usa ningún color para resaltar los cambios de revisión. |
| ByAuthor | `20` | Las revisiones de cada autor reciben su propio color para resaltar de un conjunto predefinido de colores de alto contraste. |

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

* espacio de nombres [Aspose.Words.Layout](../../aspose.words.layout/)
* asamblea [Aspose.Words](../../)


