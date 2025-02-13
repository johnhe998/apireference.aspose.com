---
title: Field.Unlink
second_title: Referencia de API de Aspose.Words para .NET
description: Field método. Realiza el desvinculado del campo.
type: docs
weight: 130
url: /es/net/aspose.words.fields/field/unlink/
---
## Field.Unlink method

Realiza el desvinculado del campo.

```csharp
public bool Unlink()
```

### Valor_devuelto

`Verdadero` si el campo ha sido desvinculado, de lo contrario`falso` .

### Observaciones

Reemplaza el campo con su resultado más reciente.

Algunos campos, como los campos XE (Entrada de índice) y los campos SEQ (Secuencia), no se pueden desvincular.

### Ejemplos

Muestra cómo desvincular un campo.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
doc.Range.Fields[1].Unlink();
```

### Ver también

* class [Field](../)
* espacio de nombres [Aspose.Words.Fields](../../field/)
* asamblea [Aspose.Words](../../../)


