---
title: Class FieldTime
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.FieldTime clase. Implementa el campo HORA.
type: docs
weight: 2350
url: /es/net/aspose.words.fields/fieldtime/
---
## FieldTime class

Implementa el campo HORA.

```csharp
public class FieldTime : Field
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [FieldTime](fieldtime/)() | Constructor predeterminado |

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

### Observaciones

Inserta la fecha y hora actual.

### Ejemplos

Muestra cómo mostrar la hora actual usando el campo HORA.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Por defecto, la hora se muestra en el formato "h:mm am/pm".
    FieldTime field = InsertFieldTime(builder, "");

    Assert.AreEqual(" TIME ", field.GetFieldCode());

    // Podemos usar la bandera \@ para cambiar el formato de nuestro tiempo mostrado.
    field = InsertFieldTime(builder, "\\@ HHmm");

    Assert.AreEqual(" TIME \\@ HHmm", field.GetFieldCode());

    // Podemos ajustar el formato para que el campo HORA también muestre la fecha, según el calendario gregoriano.
    field = InsertFieldTime(builder, "\\@ \"M/d/yyyy h mm:ss am/pm\"");

    Assert.AreEqual(" TIME \\@ \"M/d/yyyy h mm:ss am/pm\"", field.GetFieldCode());

    doc.Save(ArtifactsDir + "Field.TIME.docx");

/// <summary>
/// Use un generador de documentos para insertar un campo HORA, inserte un nuevo párrafo y devuelva el campo.
/// </summary>
private static FieldTime InsertFieldTime(DocumentBuilder builder, string format)
{
    FieldTime field = (FieldTime)builder.InsertField(FieldType.FieldTime, true);
    builder.MoveTo(field.Separator);
    builder.Write(format);
    builder.MoveTo(field.Start.ParentNode);

    builder.InsertParagraph();
    return field;
}
```

### Ver también

* class [Field](../field/)
* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


