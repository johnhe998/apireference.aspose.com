---
title: Font.NameOther
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Devuelve o establece la fuente utilizada para caracteres con códigos de carácter del 128 al 255.
type: docs
weight: 270
url: /es/net/aspose.words/font/nameother/
---
## Font.NameOther property

Devuelve o establece la fuente utilizada para caracteres con códigos de carácter del 128 al 255.

```csharp
public string NameOther { get; set; }
```

### Ejemplos

Muestra cómo Microsoft Word puede combinar dos fuentes diferentes en una sola ejecución.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Supongamos una ejecución que usamos el constructor para insertar mientras usamos esta configuración de fuente
// contiene caracteres dentro del rango de caracteres ASCII. En ese caso,
// mostrará esos caracteres usando esta fuente.
builder.Font.NameAscii = "Calibri";

// Sin otra fuente especificada, el constructor también aplicará esta fuente a todos los caracteres que inserte.
Assert.AreEqual("Calibri", builder.Font.Name);

// Especifique una fuente para usar con todos los caracteres fuera del rango ASCII.
// Idealmente, esta fuente debería tener un glifo para cada código de carácter no ASCII requerido.
builder.Font.NameOther = "Courier New";

// Inserta una secuencia con una palabra que consta de caracteres ASCII y una palabra con todos los caracteres fuera de ese rango.
// Cada carácter se mostrará usando cualquiera de las fuentes, dependiendo de.
builder.Writeln("Hello, Привет");

doc.Save(ArtifactsDir + "Font.NameAscii.docx");
```

### Ver también

* property [Name](../name/)
* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


