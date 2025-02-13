---
title: LoadOptions.Encoding
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Obtiene o establece la codificación que se usará para cargar un documento HTML TXT o CHM si la codificación no se especifica dentro del documento. Puede ser nulo. El valor predeterminado es nulo.
type: docs
weight: 50
url: /es/net/aspose.words.loading/loadoptions/encoding/
---
## LoadOptions.Encoding property

Obtiene o establece la codificación que se usará para cargar un documento HTML, TXT o CHM si la codificación no se especifica dentro del documento. Puede ser nulo. El valor predeterminado es nulo.

```csharp
public Encoding Encoding { get; set; }
```

### Observaciones

Esta propiedad se usa solo cuando se cargan documentos HTML, TXT o CHM.

Si no se especifica la codificación dentro del documento y esta propiedad es`nulo`, entonces el sistema intentará detectar automáticamente la codificación.

### Ejemplos

Muestra cómo establecer la codificación con la que abrir un documento.

```csharp
// Un objeto FileFormatInfo detectará que este archivo está codificado en algo que no sea UTF-7.
FileFormatInfo fileFormatInfo = FileFormatUtil.DetectFileFormat(MyDir + "Encoded in UTF-7.txt");

Assert.AreNotEqual(Encoding.UTF7, fileFormatInfo.Encoding);

// Si cargamos el documento sin configuraciones de carga, Aspose.Words detectará su codificación como UTF-8.
Document doc = new Document(MyDir + "Encoded in UTF-7.txt");

// Los contenidos, analizados en UTF-8, crean una cadena válida.
// Sin embargo, sabiendo que el archivo está en UTF-7, podemos ver que el resultado es incorrecto.
Assert.AreEqual("Hello world+ACE-", doc.ToString(SaveFormat.Text).Trim());

// En casos de codificación ambigua como esta, podemos establecer una variante de codificación específica
// para analizar el archivo dentro de un objeto LoadOptions.
LoadOptions loadOptions = new LoadOptions
{
    Encoding = Encoding.UTF7
};

// Cargue el documento mientras pasa el objeto LoadOptions, luego verifique el contenido del documento.
doc = new Document(MyDir + "Encoded in UTF-7.txt", loadOptions);

Assert.AreEqual("Hello world!", doc.ToString(SaveFormat.Text).Trim());
```

### Ver también

* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


