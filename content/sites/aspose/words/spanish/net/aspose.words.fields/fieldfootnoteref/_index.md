---
title: Class FieldFootnoteRef
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.FieldFootnoteRef clase. Implementa el campo FOOTNOTEREF.
type: docs
weight: 1750
url: /es/net/aspose.words.fields/fieldfootnoteref/
---
## FieldFootnoteRef class

Implementa el campo FOOTNOTEREF.

```csharp
public class FieldFootnoteRef : Field
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [FieldFootnoteRef](fieldfootnoteref/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Obtiene el texto que representa el resultado del campo mostrado. |
| [End](../../aspose.words.fields/field/end/) { get; } | Obtiene el nodo que representa el final del campo. |
| [Format](../../aspose.words.fields/field/format/) { get; } | Obtiene un[`FieldFormat`](../fieldformat/) objeto que proporciona acceso escrito al formato del campo. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Obtiene o establece si el resultado actual del campo ya no es correcto (obsoleto) debido a otras modificaciones realizadas en el documento. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Obtiene o establece si el campo está bloqueado (no debe recalcular su resultado). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Obtiene o establece el LCID del campo. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Obtiene o establece el texto que se encuentra entre el separador de campo y el final del campo. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Obtiene el nodo que representa el separador de campos. Puede ser nulo. |
| [Start](../../aspose.words.fields/field/start/) { get; } | Obtiene el nodo que representa el inicio del campo. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | Obtiene el tipo de campo de Microsoft Word. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | Devuelve el texto entre el inicio del campo y el separador de campo (o el final del campo si no hay separador). Se incluyen tanto el código de campo como el resultado de campo de los campos secundarios. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | Devuelve el texto entre el inicio del campo y el separador de campo (o el final del campo si no hay separador). |
| [Remove](../../aspose.words.fields/field/remove/)() | Elimina el campo del documento. Devuelve un nodo justo después del campo. Si el final del campo es el último hijo de su nodo principal, devuelve su párrafo principal. Si el campo ya está eliminado, devuelve **nulo** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | Realiza el desvinculado del campo. |
| [Update](../../aspose.words.fields/field/update/)() | Realiza la actualización del campo. Se lanza si el campo ya se está actualizando. |
| [Update](../../aspose.words.fields/field/update/)(bool) | Realiza una actualización de campo. Se lanza si el campo ya se está actualizando. |

### Ejemplos

Muestra cómo hacer una referencia cruzada de las notas al pie con el campo FOOTNOTEREF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("CrossRefBookmark");
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Cross referenced footnote.");
builder.EndBookmark("CrossRefBookmark");
builder.InsertParagraph();

// Insertar un campo FOOTNOTEREF, que nos permite hacer referencia a una nota al pie más de una vez mientras reutilizamos el mismo marcador de nota al pie.
builder.Write("CrossReference: ");
FieldFootnoteRef field = (FieldFootnoteRef) builder.InsertField(FieldType.FieldFootnoteRef, true);

// Referencia al marcador que hemos creado con el campo FOOTNOTEREF. Ese marcador contiene un marcador de nota al pie
// perteneciente a la nota al pie que insertamos. El campo mostrará ese marcador de nota al pie.
builder.MoveTo(field.Separator);
builder.Write("CrossRefBookmark");

Assert.AreEqual(" FOOTNOTEREF CrossRefBookmark", field.GetFieldCode());

doc.UpdateFields();

// Este campo solo funciona en versiones anteriores de Microsoft Word.
doc.Save(ArtifactsDir + "Field.FOOTNOTEREF.doc");
```

### Ver también

* class [Field](../field/)
* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


