---
title: DocumentBuilder.InsertCheckBox
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder método. Inserta un campo de formulario de casilla de verificación en la posición actual.
type: docs
weight: 270
url: /es/net/aspose.words/documentbuilder/insertcheckbox/
---
## InsertCheckBox(string, bool, int) {#insertcheckbox_1}

Inserta un campo de formulario de casilla de verificación en la posición actual.

```csharp
public FormField InsertCheckBox(string name, bool checkedValue, int size)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| name | String | El nombre del campo de formulario. Puede ser una cadena vacía. El valor de más de 20 caracteres se truncará. |
| checkedValue | Boolean | Estado comprobado del campo de formulario de casilla de verificación. |
| size | Int32 | Especifica el tamaño de la casilla de verificación en puntos. Especifique 0 para MS Word para calcular el tamaño de la casilla de verificación automáticamente. |

### Valor_devuelto

El nodo de campo de formulario que se acaba de insertar.

### Observaciones

Si especifica un nombre para el campo de formulario, se crea automáticamente un marcador con el mismo nombre.

### Ejemplos

Muestra cómo insertar casillas de verificación en el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte casillas de verificación de diferentes tamaños y estados marcados predeterminados.
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// Los campos de formulario tienen un límite de longitud de nombre de 20 caracteres.
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// Podemos interactuar con estas casillas de verificación en Microsoft Word haciendo doble clic en ellas.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### Ver también

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)

---

## InsertCheckBox(string, bool, bool, int) {#insertcheckbox}

Inserta un campo de formulario de casilla de verificación en la posición actual.

```csharp
public FormField InsertCheckBox(string name, bool defaultValue, bool checkedValue, int size)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| name | String | El nombre del campo de formulario. Puede ser una cadena vacía. El valor de más de 20 caracteres se truncará. |
| defaultValue | Boolean | Valor predeterminado del campo de formulario de casilla de verificación. |
| checkedValue | Boolean | Estado actual de verificación del campo de formulario de casilla de verificación. |
| size | Int32 | Especifica el tamaño de la casilla de verificación en puntos. Especifique 0 para MS Word para calcular el tamaño de la casilla de verificación automáticamente. |

### Valor_devuelto

El nodo de campo de formulario que se acaba de insertar.

### Observaciones

Si especifica un nombre para el campo de formulario, se crea automáticamente un marcador con el mismo nombre.

### Ejemplos

Muestra cómo insertar casillas de verificación en el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte casillas de verificación de diferentes tamaños y estados marcados predeterminados.
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// Los campos de formulario tienen un límite de longitud de nombre de 20 caracteres.
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// Podemos interactuar con estas casillas de verificación en Microsoft Word haciendo doble clic en ellas.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### Ver también

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


