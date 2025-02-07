---
title: MailMerge.UnconditionalMergeFieldsAndRegions
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge propiedad. Obtiene o establece un valor que indica si los campos de fusión y las regiones de fusión se fusionan independientemente de la condición del campo IF principal.
type: docs
weight: 140
url: /es/net/aspose.words.mailmerging/mailmerge/unconditionalmergefieldsandregions/
---
## MailMerge.UnconditionalMergeFieldsAndRegions property

Obtiene o establece un valor que indica si los campos de fusión y las regiones de fusión se fusionan independientemente de la condición del campo IF principal.

```csharp
public bool UnconditionalMergeFieldsAndRegions { get; set; }
```

### Observaciones

El valor predeterminado es **falso** .

### Ejemplos

Muestra cómo fusionar campos o regiones independientemente de la condición del campo IF principal.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta un MERGEFIELD anidado dentro de un campo IF.
// Dado que la declaración del campo IF es falsa, no mostrará el resultado de MERGEFIELD.
// El MERGEFIELD tampoco recibirá ningún dato durante una combinación de correspondencia.
FieldIf fieldIf = (FieldIf)builder.InsertField(" IF 1 = 2 ");
builder.MoveTo(fieldIf.Separator);
builder.InsertField(" MERGEFIELD  FullName ");

// Si establecemos el indicador "UnconditionalMergeFieldsAndRegions" en "verdadero",
// nuestra combinación de correo insertará datos en los campos que no se muestran, como nuestro MERGEFIELD y todos los demás.
// Si establecemos el indicador "UnconditionalMergeFieldsAndRegions" en "falso",
// nuestra combinación de correo no insertará datos en MERGEFIELD ocultos por campos IF con declaraciones falsas.
doc.MailMerge.UnconditionalMergeFieldsAndRegions = countAllMergeFields;

DataTable dataTable = new DataTable();
dataTable.Columns.Add("FullName");
dataTable.Rows.Add("James Bond");

doc.MailMerge.Execute(dataTable);

doc.Save(ArtifactsDir + "MailMerge.UnconditionalMergeFieldsAndRegions.docx");

Assert.AreEqual(
    countAllMergeFields
        ? "\u0013 IF 1 = 2 \"James Bond\"\u0014\u0015"
        : "\u0013 IF 1 = 2 \u0013 MERGEFIELD  FullName \u0014«FullName»\u0015\u0014\u0015",
    doc.GetText().Trim());
```

### Ver también

* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


