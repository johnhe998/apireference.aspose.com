---
title: Enum StoryType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.StoryType enumeración. El texto de un documento de Word se almacena en historias. Tipo de historia identifica una historia.
type: docs
weight: 5820
url: /es/net/aspose.words/storytype/
---
## StoryType enumeration

El texto de un documento de Word se almacena en historias. **Tipo de historia** identifica una historia.

```csharp
public enum StoryType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| None | `0` | Valor por defecto. No hay tal historia en el documento. |
| MainText | `1` | Contiene el texto principal del documento, representado por[`Body`](../body/) . |
| Footnotes | `2` | Contiene texto de nota al pie, representado por[`Footnote`](../../aspose.words.notes/footnote/) . |
| Endnotes | `3` | Contiene texto de notas al final, representado por[`Footnote`](../../aspose.words.notes/footnote/) . |
| Comments | `4` | Contiene comentarios del documento (anotaciones), representados por[`Comment`](../comment/) . |
| Textbox | `5` | Contiene forma o texto de cuadro de texto, representado por[`Shape`](../../aspose.words.drawing/shape/) . |
| EvenPagesHeader | `6` | Contiene el texto del encabezado de las páginas pares, representado por[`HeaderFooter`](../headerfooter/) . |
| PrimaryHeader | `7` | Contiene texto del encabezado principal. Cuando el encabezado es diferente para las páginas pares e impares, contiene el texto del encabezado de las páginas impares. Representado por[`HeaderFooter`](../headerfooter/) . |
| EvenPagesFooter | `8` | Contiene el texto del pie de página de las páginas pares, representado por[`HeaderFooter`](../headerfooter/) . |
| PrimaryFooter | `9` | Contiene el texto del pie de página principal. Cuando el pie de página es diferente para las páginas pares e impares, contiene el texto del pie de página de las páginas impares. Representado por[`HeaderFooter`](../headerfooter/) . |
| FirstPageHeader | `10` | Contiene el texto del encabezado de la primera página, representado por[`HeaderFooter`](../headerfooter/) . |
| FirstPageFooter | `11` | Contiene el texto del pie de página de la primera página, representado por[`HeaderFooter`](../headerfooter/) . |
| FootnoteSeparator | `12` | Contiene el texto del separador de nota al pie, representado porFootnoteSeparator . |
| FootnoteContinuationSeparator | `13` | Contiene el texto del separador de continuación de nota al pie, representado porFootnoteSeparator . |
| FootnoteContinuationNotice | `14` | Contiene el texto del separador de aviso de continuación de nota al pie, representado porFootnoteSeparator . |
| EndnoteSeparator | `15` | Contiene el texto del separador de notas al final, representado porFootnoteSeparator . |
| EndnoteContinuationSeparator | `16` | Contiene el texto del separador de continuación de notas al final, representado porFootnoteSeparator . |
| EndnoteContinuationNotice | `17` | Contiene el texto del separador de aviso de continuación de notas al final, representado porFootnoteSeparator . |

### Ejemplos

Muestra cómo eliminar todas las formas de un nodo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Usa un DocumentBuilder para insertar una forma. Esta es una forma en línea,
// que tiene un Párrafo principal, que es un nodo secundario del Cuerpo de la primera sección.
builder.InsertShape(ShapeType.Cube, 100.0, 100.0);

Assert.AreEqual(1, doc.GetChildNodes(NodeType.Shape, true).Count);

// Podemos eliminar todas las formas de los párrafos secundarios de este Cuerpo.
Assert.AreEqual(StoryType.MainText, doc.FirstSection.Body.StoryType);
doc.FirstSection.Body.DeleteShapes();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Shape, true).Count);
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


