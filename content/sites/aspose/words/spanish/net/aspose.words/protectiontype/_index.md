---
title: Enum ProtectionType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.ProtectionType enumeración. Tipo de protección para un documento.
type: docs
weight: 4260
url: /es/net/aspose.words/protectiontype/
---
## ProtectionType enumeration

Tipo de protección para un documento.

```csharp
public enum ProtectionType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| AllowOnlyComments | `1` | El usuario solo puede modificar comentarios en el documento. |
| AllowOnlyFormFields | `2` | El usuario solo puede ingresar datos en los campos del formulario en el documento. |
| AllowOnlyRevisions | `0` | El usuario solo puede agregar marcas de revisión al documento. |
| ReadOnly | `3` | No se permiten cambios en el documento. Disponible desde Microsoft Word 2003. |
| NoProtection | `-1` | El documento no está protegido. |

### Ejemplos

Muestra cómo desactivar la protección de una sección.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Aplicar protección contra escritura a cada sección del documento.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// Desactiva la protección contra escritura para la primera sección.
doc.Sections[0].ProtectedForForms = false;

// En este documento de salida, podremos editar la primera sección libremente,
// y solo podremos editar el contenido del campo del formulario en la segunda sección.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


