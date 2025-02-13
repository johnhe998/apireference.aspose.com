---
title: FieldOptions.IsBidiTextSupportedOnUpdate
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Obtiene o establece el valor que indica si el texto bidireccional es totalmente compatible durante la actualización del campo o no.
type: docs
weight: 130
url: /es/net/aspose.words.fields/fieldoptions/isbiditextsupportedonupdate/
---
## FieldOptions.IsBidiTextSupportedOnUpdate property

Obtiene o establece el valor que indica si el texto bidireccional es totalmente compatible durante la actualización del campo o no.

```csharp
public bool IsBidiTextSupportedOnUpdate { get; set; }
```

### Observaciones

Cuando esta propiedad se establece en **verdadero**, se realizan pasos adicionales para producir un resultado de campo compatible de derecha a izquierda language (es decir, árabe o hebreo) durante su actualización.

Cuando esta propiedad se establece en **falso** y se utiliza lenguaje de derecha a izquierda, no se garantiza la corrección del campo result después de su actualización.

El valor predeterminado es **falso**.

### Ejemplos

Muestra cómo usar FieldOptions para garantizar que la actualización de campos admita completamente el texto bidireccional.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Asegúrese de que cualquier operación de campo que involucre texto de derecha a izquierda se realice como se esperaba. 
doc.FieldOptions.IsBidiTextSupportedOnUpdate = true;

// Use un generador de documentos para insertar un campo que contenga el texto de derecha a izquierda.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "עֶשְׂרִים", "שְׁלוֹשִׁים", "אַרְבָּעִים", "חֲמִשִּׁים", "שִׁשִּׁים" }, 0);
comboBox.CalculateOnExit = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.Bidi.docx");
```

### Ver también

* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


