---
title: IFieldUpdatingCallback.FieldUpdating
second_title: Referencia de API de Aspose.Words para .NET
description: IFieldUpdatingCallback método. Un método definido por el usuario que se llama justo antes de que se actualice un campo.
type: docs
weight: 20
url: /es/net/aspose.words.fields/ifieldupdatingcallback/fieldupdating/
---
## IFieldUpdatingCallback.FieldUpdating method

Un método definido por el usuario que se llama justo antes de que se actualice un campo.

```csharp
public void FieldUpdating(Field field)
```

### Ejemplos

Muestra cómo usar métodos de devolución de llamada durante una actualización de campo.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
    builder.InsertField(" TIME ");
    builder.InsertField(" REVNUM ");
    builder.InsertField(" AUTHOR  \"John Doe\" ");
    builder.InsertField(" SUBJECT \"My Subject\" ");
    builder.InsertField(" QUOTE \"Hello world!\" ");

    FieldUpdatingCallback callback = new FieldUpdatingCallback();
    doc.FieldOptions.FieldUpdatingCallback = callback;

    doc.UpdateFields();

    Assert.True(callback.FieldUpdatedCalls.Contains("Updating John Doe"));
}

/// <summary>
/// Implemente esta interfaz si desea tener sus propios métodos personalizados llamados durante una actualización de campo.
/// </summary>
public class FieldUpdatingCallback : IFieldUpdatingCallback
{
    public FieldUpdatingCallback()
    {
        FieldUpdatedCalls = new List<string>();
    }

    /// <summary>
    /// Un método definido por el usuario que se llama justo antes de que se actualice un campo.
    /// </summary>
    void IFieldUpdatingCallback.FieldUpdating(Field field)
    {
        if (field.Type == FieldType.FieldAuthor)
        {
            FieldAuthor fieldAuthor = (FieldAuthor) field;
            fieldAuthor.AuthorName = "Updating John Doe";
        }
    }

    /// <summary>
    /// Un método definido por el usuario que se llama justo después de actualizar un campo.
    /// </summary>
    void IFieldUpdatingCallback.FieldUpdated(Field field)
    {
        FieldUpdatedCalls.Add(field.Result);
    }

    public IList<string> FieldUpdatedCalls { get; }
}
```

### Ver también

* class [Field](../../field/)
* interface [IFieldUpdatingCallback](../)
* espacio de nombres [Aspose.Words.Fields](../../ifieldupdatingcallback/)
* asamblea [Aspose.Words](../../../)


