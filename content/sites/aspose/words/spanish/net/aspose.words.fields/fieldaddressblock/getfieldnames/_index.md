---
title: FieldAddressBlock.GetFieldNames
second_title: Referencia de API de Aspose.Words para .NET
description: FieldAddressBlock método. Devuelve una colección de nombres de campos de combinación de correspondencia usados por el campo.
type: docs
weight: 70
url: /es/net/aspose.words.fields/fieldaddressblock/getfieldnames/
---
## FieldAddressBlock.GetFieldNames method

Devuelve una colección de nombres de campos de combinación de correspondencia usados por el campo.

```csharp
public string[] GetFieldNames()
```

### Ejemplos

Muestra cómo obtener nombres de campos de combinación de correspondencia utilizados por un campo.

```csharp
Document doc = new Document(MyDir + "Field sample - ADDRESSBLOCK.docx");

string[] addressFieldsExpect =
{
    "Company", "First Name", "Middle Name", "Last Name", "Suffix", "Address 1", "City", "State",
    "Country or Region", "Postal Code"
};

FieldAddressBlock addressBlockField = (FieldAddressBlock) doc.Range.Fields[0];
string[] addressBlockFieldNames = addressBlockField.GetFieldNames();
```

### Ver también

* class [FieldAddressBlock](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldaddressblock/)
* asamblea [Aspose.Words](../../../)


